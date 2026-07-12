# Fila-Food

Aplicação web para gerenciamento digital de filas em estabelecimentos de alimentação.

O projeto foi desenvolvido durante o **Mega Hack 3ª Edição**, promovido pela Shawee, no desafio do **SEBRAE / MCTIC**, voltado ao setor de alimentação fora do lar.

## Problema

Durante a pandemia, a capacidade de atendimento de restaurantes e outros estabelecimentos foi reduzida. Como consequência, clientes passaram a aguardar em filas externas, aumentando o risco de aglomeração.

## Solução

O Fila-Food propõe uma fila virtual para restaurantes.

O cliente pode entrar na fila pelo sistema e aguardar sua vez fora do estabelecimento, como em casa ou no carro, de acordo com o tempo máximo de espera definido pelo restaurante.

## Funcionalidades principais

- Cadastro de clientes;
- Cadastro de restaurantes;
- Cadastro e gerenciamento de mesas;
- Entrada de clientes na fila;
- Consulta da fila por restaurante ou cliente;
- Atualização e remoção de registros da fila;
- Painel de controle para acompanhamento do atendimento;
- Localização de restaurantes por mapa.

## Tecnologias utilizadas

### Frontend

- React;
- TypeScript;
- Axios;
- React Router;
- React Leaflet;
- CSS.

### Backend

- Node.js;
- Express;
- TypeScript;
- Knex;
- SQLite;
- CORS.

## Estrutura do projeto

```text
fila-food/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── database/
│   │   │   ├── migrations/
│   │   │   └── seeds/
│   │   ├── routes.ts
│   │   └── server.ts
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── assets/
│   └── package.json
└── ANALISE_RISCOS.md
```

## Como executar

### Pré-requisitos

- Node.js;
- npm ou Yarn.

### Backend

Acesse a pasta do backend:

```bash
cd backend
```

Instale as dependências:

```bash
npm install
```

Execute as migrations:

```bash
npm run knex:migrate
```

Execute os seeds:

```bash
npm run knex:seed
```

Inicie a API:

```bash
npm run dev
```

A API será executada, por padrão, na porta:

```text
http://localhost:3333
```

### Frontend

Em outro terminal, acesse a pasta do frontend:

```bash
cd frontend
```

Instale as dependências:

```bash
npm install
```

Inicie a aplicação:

```bash
npm start
```

A aplicação será executada, por padrão, em:

```text
http://localhost:3000
```

## Análise de riscos

Foi realizada uma análise dos principais riscos técnicos e operacionais do projeto com apoio de Inteligência Artificial Generativa.

A análise está disponível no arquivo:

[ANALISE_RISCOS.md](./ANALISE_RISCOS.md)

## Limitações atuais

Este projeto foi desenvolvido como protótipo de hackathon e não está pronto para uso em produção.

Entre as principais limitações estão:

- autenticação simplificada;
- senhas armazenadas sem hash;
- ausência de controle de autorização por perfil;
- falta de validação completa dos dados;
- uso de SQLite;
- ausência de testes automatizados;
- dependências desatualizadas;
- funcionalidades ainda não implementadas.

## Objetivo acadêmico

O projeto foi utilizado como cenário prático para avaliação de riscos em projetos de software.

A implementação original foi realizada sem apoio de Inteligência Artificial. A IA foi utilizada posteriormente para apoiar a análise dos riscos, a organização das informações e a definição inicial de estratégias de resposta.

## Licença

Projeto de caráter educacional e experimental.
