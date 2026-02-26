# Board Project

Um gerenciador de tarefas e issues moderno, construído com as tecnologias mais recentes do ecossistema React e Next.js.

## 🚀 Tecnologias

Este projeto utiliza uma stack robusta e performática:

- **Framework**: [Next.js 16](https://nextjs.org/) (App Router)
- **Linguagem**: [TypeScript](https://www.typescriptlang.org/)
- **API**: [Hono](https://hono.dev/) (integrado via Route Handlers)
- **Banco de Dados**: [PostgreSQL](https://www.postgresql.org/)
- **ORM**: [Drizzle ORM](https://orm.drizzle.team/)
- **Autenticação**: [Better Auth](https://www.better-auth.com/)
- **Estilização**: [Tailwind CSS v4](https://tailwindcss.com/)
- **Gerenciamento de Estado/Cache**: [TanStack Query](https://tanstack.com/query/latest)
- **Validação**: [Zod](https://zod.dev/)
- **Linting/Formatting**: [Biome](https://biomejs.dev/)
- **Git Hooks**: [Lefthook](https://github.com/evilmartians/lefthook)

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- [Node.js](https://nodejs.org/) (versão 20 ou superior)
- [pnpm](https://pnpm.io/) (gerenciador de pacotes)
- [Docker](https://www.docker.com/) & Docker Compose (para o banco de dados)

## 🛠️ Instalação e Configuração

1. **Clone o repositório:**

```bash
git clone <seu-repositorio-url>
cd board
```

2. **Instale as dependências:**

```bash
pnpm install
```

3. **Configure as variáveis de ambiente:**

Crie um arquivo `.env` na raiz do projeto com base no exemplo (se houver) ou configure as chaves necessárias, principalmente a conexão com o banco de dados.

```env
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/board"
# Adicione outras variáveis necessárias para o Better Auth e API
```

4. **Suba o banco de dados:**

Utilize o Docker Compose para iniciar o container do PostgreSQL:

```bash
docker-compose up -d
```

5. **Configure o banco de dados (Migrations & Seed):**

Execute as migrações para criar as tabelas e, opcionalmente, o seed para popular com dados iniciais.

```bash
# Gera as migrações com base no schema
pnpm db:generate

# Aplica as migrações no banco
pnpm db:migrate

# (Opcional) Popula o banco com dados de teste
pnpm db:seed
```

## ▶️ Executando o Projeto

Para iniciar o servidor de desenvolvimento:

```bash
pnpm dev
```

Acesse [http://localhost:3000](http://localhost:3000) no seu navegador.

## 📜 Scripts Disponíveis

- `pnpm dev`: Inicia o servidor de desenvolvimento.
- `pnpm build`: Cria a build de produção.
- `pnpm start`: Inicia o servidor de produção.
- `pnpm lint`: Verifica problemas de linting com Biome.
- `pnpm format`: Formata o código automaticamente com Biome.
- `pnpm db:generate`: Gera arquivos SQL de migração baseados no schema do Drizzle.
- `pnpm db:migrate`: Aplica as migrações pendentes ao banco de dados.
- `pnpm db:studio`: Abre o Drizzle Studio para visualizar/editar o banco de dados no navegador.

## 📂 Estrutura do Projeto

- `src/app`: Páginas e rotas do Next.js (App Router).
- `src/api`: Definições da API, configuração do banco de dados (Drizzle) e schemas.
  - `db`: Schemas, migrations e seeds do banco.
  - `routes`: Definições das rotas da API Hono.
- `src/components`: Componentes reutilizáveis da UI.
- `src/http`: Funções auxiliares para requisições HTTP (fetchers).
- `src/lib`: Configurações de bibliotecas (React Query, Auth Client).
