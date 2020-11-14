# Opinião sobre o desafio:

Antes queria comentar um pouco sobre minha experiência, sou dev PHP e Node.js e já trabalhei um pouco com Vue.js.

A parte do backend achei bem legal por ter mais experiência com backend e api's rest,
já desenvolvi projetos com express e é sempre muito bom programador em Node.

O frontend também curti por que já trabalhei com vue e prefiro ele até mais que react que é um pouco mais famoso entre os dev's, só nunca tinha usado ele com o vuetify, já tinha conhecimento sobre a existência do vuetify porem nunca tinha colocado a mão na massa, curti bastante, bem agradável de desenvolver.

Sobre a stack eu me senti bem confortável por já ter experiência com as tecnologias.

## Decisão da arquitetura utilizada

### Backend:

Foi utilizado Node e Express conforme solicitado, porém acrescentei o Typescript por que além de acrescentar a tipagem e ajudar a IDE a saber os formatos de paramêtros e objetos, também permite incluir funcionalidades que não chegaram no Node de forma nativa por exemplo import/export, o banco de dados preferi utilizar o Postgress por preferência mesmo, apesar de minha experiência de trabalho ser 80% usando Mysql.

### Frontend:

Foi utilizado Vue.js e o Vuetify, porém tambem acrescentei o Typescript, fiquei curioso para implementar um app com Vue e Typescript, já que só tinha utilizado antes com js normalmente.

## Lista de bibliotecas de terceiros utilizadas

### Backend:

- Express (pré requisito)
- Typeorm (Preferência por achar mais tranquilo de trabalhar com repositories, criando uma camada responsável só pra acesso ao banco de dados, apesar de conhecer o sequelize)
- Reflect-metadata (dependência do Typeorm)
- Pg (para trabalhar com postgress com o Typeorm)
- Yup (para validações server side, sempre bom ter validações em ambas as partes)
- Cors (para configuração de acesso a api)
- Jest (desenvolvimento)(para testes)
- Supertest (desenvolvimento)(para testar api's em node, com jest)
- Ts-jest (desenvolvimento)(para trabalhar com jest e typescript)
- faker (desenvolvimento)(para criar dados falsos para serem utilizados nos testes)
- Typescript (desenvolvimento)(para utilizar o node com as features do typescript)
- Ts-node-dev (desenvolvimento)(para compilar o typescript e restartar o servidor sempre que houver mudanças no código)
- Env-cmd (desenvolvimento) (para trabalhar com variáveis de ambiente no desenvolvimento local)

### Frontend:

- Vuetifyjs (pré requisito)
- Vue Router (controlar rotas da aplicação)
- Axios (solicitações HTTP)
- Vuex (gerenciamento de estado)
- V-mask (para usar mascaras em campos de texto)
- Typescript (desenvolvilmento) (para utilizar o Vue com as features do typescript)
- Eslint (desenvolvimento) (manter o código organizado e dentro dos padrões)

## O que você melhoraria se tivesse mais tempo

Implementaria mais funcionalidades além das que foram pedidas e me aprofundaria mais nos testes no backend, e implementaria testes no frontend, que acabei optando por não fazer, por ter sido uma semana em que estive bastante sem tempo.

## Quais requisitos obrigatórios que não foram entregues

Todos os requisitos obrigatórios foram entregues

## Instruções para startar a api e o frontend

### Backend

- Criar os arquivos .env e o .env.test utilizando como base o .env.example e configurando as variaveis de acordo com o seu ambiente
- Comando `npm run dev` para startar a api em desenvolvimento, isto irá criar automaticamente o banco de dados com o nome configurado no arquivo .env
- Comando `npm run test` para startar os testes com jest, também irá criar automaticamente o banco de dados de teste com as configurações adicionadas no .env.test

### Frontend

- Criar o arquivo .env utilizando como base o .env.example e configurar a variavel que guarda o endereço base da api, sem esquecer de por o http://

## OBS: deixei disponível uma collection do postman
