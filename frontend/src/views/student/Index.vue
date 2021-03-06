<template>
  <v-card>
    <v-container class="pa-5">
      <v-row class="mb-7">
        <v-col lg="8" md="7" sm="12">
          <search-text-input @trigger-search="search" />
        </v-col>
        <v-spacer />
        <v-col lg="3" md="3" sm="12">
          <v-btn color="secondary" :to="{ name: 'student.create' }" large>Cadastrar Aluno</v-btn>
        </v-col>
      </v-row>
      <v-row>
        <v-col md="12">
          <v-data-table
            disable-pagination
            :loading="loading"
            :headers="headers"
            :items="students"
            :hide-default-footer="true"
            class="elevation-1"
          >
            <template v-slot:[`item.cpf`]="{ item }">
              {{ item.cpf | VMask('###.###.###-##') }}
            </template>
            <template v-slot:[`item.actions`]="{ item }">
              <v-tooltip top>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    v-on="on"
                    v-bind="attrs"
                    icon
                    :to="{ name: 'student.edit', params: { id: item.id } }"
                  >
                    <v-icon>
                      mdi-lead-pencil
                    </v-icon>
                  </v-btn>
                </template>
                <span>Editar</span>
              </v-tooltip>

              <modal-delete-button :student-id="item.id" @delete-callback="deleteCallback" />
            </template>
          </v-data-table>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
<script lang="ts">
import Vue from 'vue';
import StudentService, { Student } from '../../services/studentService';
import SearchTextInput from '../../components/SearchTextInput.vue';
import ModalDeleteButton from './ModalDelete.vue';

interface ComponentData {
  loading: boolean;
  headers: {
    text: string;
    value: string;
  }[];
  students: Student[];
}

export default Vue.extend({
  name: 'Students',
  data() {
    return {
      loading: false,
      headers: [
        {
          text: 'Registro Acadêmico',
          value: 'ra',
        },
        {
          text: 'Nome',
          value: 'name',
        },
        {
          text: 'CPF',
          value: 'cpf',
        },
        {
          text: 'Ações',
          value: 'actions',
        },
      ],
      students: [],
    } as ComponentData;
  },
  components: {
    SearchTextInput,
    ModalDeleteButton,
  },
  async created() {
    this.loading = true;
    const response = await StudentService.getAll();
    this.loading = false;

    if (response.status === 200) {
      this.setStudents(response.data);
    }
  },
  methods: {
    setStudents(students: Student[]) {
      this.students = students;
    },
    async search(text: string) {
      this.loading = true;
      const response = await StudentService.getAll(text);
      this.loading = false;

      if (response.status === 200) {
        this.setStudents(response.data);
      }
    },
    deleteCallback({ isDeleted, id }: { isDeleted: boolean; id: number }) {
      if (isDeleted) {
        this.students = this.students.filter((student) => student.id !== id);
      }
    },
  },
});
</script>
