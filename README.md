# API de Gerenciamento de Livros

Este projeto consiste no desenvolvimento de uma API para gerenciar uma coleção de livros, utilizando **Test Driven Development (TDD)**.

## Tecnologias Utilizadas

- **Node.js** com **Express** para construção da API
- **TDD (Test Driven Development)** para garantir a qualidade do código
- **Zod** para validação de dados
- **Helmet** para segurança da aplicação
- **express-async-errors** para tratamento de erros assíncronos

## Funcionalidades

### 1. CRUD de Livros
A API permite criar, listar, atualizar e excluir livros. Abaixo estão as principais rotas:

- `POST /books`: Criação de um livro com validação de título, número de páginas e categoria.
- `GET /books`: Listagem de todos os livros, com a opção de buscar por um termo no nome do livro utilizando query params.
- `PATCH /books/:id`: Atualização de um livro, permitindo alterar título, número de páginas e categoria.
- `DELETE /books/:id`: Exclusão de um livro pelo ID.

### 2. Validação de Dados
Foi implementado um middleware de validação com **Zod** para garantir a integridade dos dados recebidos nas requisições. Esse middleware valida o corpo da requisição (`req.body`), os parâmetros (`req.params`) e as query strings (`req.query`). Em caso de erro, a API retorna um status **409 Conflict** com os detalhes.

### 3. Segurança com Helmet
Para garantir a segurança da aplicação, o **Helmet** foi configurado no arquivo `app.ts`. Ele adiciona cabeçalhos de segurança HTTP para proteger a API contra vulnerabilidades comuns.

### 4. Busca por Nome
A rota `GET /books` permite filtrar os livros com base em um termo de busca. Se o parâmetro `search` for fornecido, a API realiza um filtro nos livros cujo nome contém o termo fornecido.

## Testes
Os testes foram fornecidos e substituídos pela pasta `tests` do projeto. Para executar os testes, basta rodar o comando:

```bash
npm run test