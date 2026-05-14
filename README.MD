# Formula 1 API

API desenvolvida no bootcamp da DIO para praticar backend com Node.js, TypeScript e Fastify. O projeto disponibiliza dados simples de equipes e pilotos de Fórmula 1, com rotas para listar informações e buscar um piloto pelo ID.

## Funcionalidades

- Listar equipes de Fórmula 1.
- Listar pilotos cadastrados.
- Buscar piloto pelo ID.
- Retornar erro quando o piloto não for encontrado.
- Permitir requisições externas com CORS.

## Tecnologias

- Node.js
- TypeScript
- Fastify
- @fastify/cors
- TSX
- TSUP

## Como executar

Instale as dependências:

```bash
npm install
```

Execute em desenvolvimento:

```bash
npm run start:dev
```

A API roda em:

```txt
http://localhost:3333
```

## Rotas

```http
GET /teams
```

```http
GET /drivers
```

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

Caso o piloto não seja encontrado:

```json
{
  "message": "Driver Not Found"
}
```

## Scripts

```json
{
  "dist": "tsup src",
  "start:dev": "tsx --env-file=.env src/server.ts",
  "start:watch": "tsx watch --env-file=.env  src/server.ts",
  "start:dist": "npm run dist && node dist/server.js"
}
```

## Build

Para gerar a versão compilada:

```bash
npm run dist
```

Para compilar e executar:

```bash
npm run start:dist
```

## Aprendizados

Neste projeto foram praticados conceitos de criação de APIs REST com Fastify, configuração de rotas, uso de TypeScript no backend, retorno de respostas JSON e organização inicial de um servidor Node.js.

## Melhorias futuras

- Separar dados, rotas e controllers em arquivos próprios.
- Adicionar mais pilotos e equipes.
- Criar testes automatizados.
- Usar variáveis de ambiente para configurar a porta.
- Conectar a API a um banco de dados.
