# Formula 1 API

API criada durante o bootcamp da DIO para praticar backend com Node.js, TypeScript e Fastify. O projeto disponibiliza dados simples sobre equipes e pilotos de Fórmula 1, permitindo consultar listas completas e buscar um piloto específico pelo ID.

## Sobre o projeto

Este repositório foi desenvolvido como exercício prático de criação de uma API REST. A proposta é entender como configurar um servidor com Fastify, criar rotas, trabalhar com respostas em JSON e organizar uma aplicação backend em TypeScript.

Os dados usados pela API estão definidos diretamente no arquivo `src/server.ts`, simulando uma base simples para consulta.

## Funcionalidades

- Listar equipes de Fórmula 1.
- Listar pilotos cadastrados.
- Buscar piloto pelo ID.
- Retornar erro quando o piloto não for encontrado.
- Permitir requisições externas com CORS.

## Tecnologias utilizadas

- Node.js
- TypeScript
- Fastify
- @fastify/cors
- TSX
- TSUP

## Rotas

O servidor roda na porta `3333`.

### Listar equipes

```http
GET /teams
```

Exemplo:

```txt
http://localhost:3333/teams
```

### Listar pilotos

```http
GET /drivers
```

Exemplo:

```txt
http://localhost:3333/drivers
```

### Buscar piloto por ID

```http
GET /drivers/:id
```

Exemplo:

```txt
http://localhost:3333/drivers/1
```

## Exemplo de resposta

```json
{
  "driver": {
    "id": 1,
    "name": "Max Verstappen",
    "team": "Red Bull Racing"
  }
}
```

Caso o ID não exista, a API retorna:

```json
{
  "message": "Driver Not Found"
}
```

## Como rodar

Instale as dependências:

```bash
npm install
```

Crie ou mantenha o arquivo `.env` na raiz do projeto:

```env
PORT=3333
```

Execute em desenvolvimento:

```bash
npm run start:dev
```

Para rodar com atualização automática ao salvar:

```bash
npm run start:watch
```

## Scripts

```json
{
  "dist": "tsup src",
  "start:dev": "tsx --env-file=.env src/server.ts",
  "start:watch": "tsx watch --env-file=.env  src/server.ts",
  "start:dist": "npm run dist && node dist/src/index.js"
}
```

## Estrutura

```txt
src/
  server.ts
```

## Aprendizados

Neste projeto foram praticados conceitos de criação de APIs com Fastify, configuração de servidor HTTP, tipagem com TypeScript, criação de rotas, retorno de status HTTP e organização inicial de uma aplicação backend.

## Melhorias futuras

- Separar os dados em arquivos próprios.
- Criar controllers e services.
- Ajustar IDs duplicados na lista de pilotos.
- Adicionar mais informações sobre equipes e pilotos.
- Criar testes automatizados para as rotas.
