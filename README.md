# Sistema de Gerenciamento de Clínica de Saúde Mental

Este é um monorepo que contém o frontend (aplicação web) e o backend (API) para um sistema de gerenciamento de clínica de saúde mental.

## Estrutura do Projeto

```
.
├── artifacts/
│   ├── api-server/             # Backend (Node.js, Express, TypeScript)
│   └── clinica/                # Frontend (React, Vite, TypeScript)
├── lib/                        # Bibliotecas compartilhadas (API clients, Zod schemas, DB)
│   ├── api-client-react/
│   ├── api-spec/
│   ├── api-zod/
│   └── db/
├── package.json                # Configurações do monorepo (pnpm workspace)
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
└── README.md                   # Este arquivo
```

## Tecnologias Utilizadas

### Frontend (`artifacts/clinica`)

- **React**: Biblioteca JavaScript para construção de interfaces de usuário.
- **Vite**: Ferramenta de build rápido para projetos web.
- **TypeScript**: Superset de JavaScript que adiciona tipagem estática.
- **Tailwind CSS**: Framework CSS utilitário para estilização rápida.
- **Radix UI**: Componentes de UI acessíveis e personalizáveis.
- **TanStack Query**: Para gerenciamento de estado assíncrono.

### Backend (`artifacts/api-server`)

- **Node.js**: Ambiente de execução JavaScript.
- **Express**: Framework web para Node.js.
- **TypeScript**: Superset de JavaScript que adiciona tipagem estática.
- **Drizzle ORM**: ORM para TypeScript com foco em tipagem e performance.
- **MySQL**: Banco de dados relacional.
- **Pino**: Logger de alta performance.

### Bibliotecas Compartilhadas (`lib/`)

- **api-client-react**: Cliente de API gerado automaticamente para React Query.
- **api-spec**: Definição da API usando OpenAPI (Swagger).
- **api-zod**: Schemas de validação da API usando Zod.
- **db**: Configuração do Drizzle ORM e schemas do banco de dados.

## Configuração Local

### Pré-requisitos

- [Node.js](https://nodejs.org/) (versão 18 ou superior)
- [pnpm](https://pnpm.io/installation) (gerenciador de pacotes)
- [MySQL Server](https://dev.mysql.com/doc/mysql-getting-started/en/) (para desenvolvimento local)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Passos de Instalação

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    cd seu-repositorio
    ```

2.  **Instale as dependências:**
    Este projeto usa `pnpm workspaces`. Certifique-se de ter o `pnpm` instalado.
    ```bash
    pnpm install
    ```

3.  **Configure o banco de dados MySQL:**
    Crie um banco de dados MySQL localmente e um usuário com permissões adequadas. Você pode usar o `mysql_schema.sql` (se disponível) para criar as tabelas.

4.  **Configure as variáveis de ambiente:**
    Crie um arquivo `.env` na raiz do projeto (`/home/ubuntu/projeto-analise/.env`) e configure as variáveis de ambiente para o backend e o frontend. Exemplo:
    
    ```env
    # Backend
    DATABASE_URL="mysql://user:password@host:port/database_name"
    JWT_SECRET="sua_chave_secreta_jwt"
    
    # Frontend
    VITE_API_BASE_URL="http://localhost:3000" # Ou a URL do seu backend
    ```
    
    **Nota**: Para o Railway, a `DATABASE_URL` será fornecida automaticamente.

5.  **Execute o projeto:**
    Para iniciar o backend e o frontend em modo de desenvolvimento:
    ```bash
    pnpm dev
    ```
    
    Isso iniciará o servidor de desenvolvimento do frontend (geralmente em `http://localhost:5173`) e o servidor da API (geralmente em `http://localhost:3000`).

## Deploy

Este projeto pode ser implantado em plataformas como Render, Railway, Vercel, etc. As configurações específicas de deploy dependerão da plataforma escolhida.

### Considerações para Deploy

-   **Variáveis de Ambiente**: Certifique-se de configurar todas as variáveis de ambiente necessárias na sua plataforma de deploy (ex: `DATABASE_URL`, `JWT_SECRET`, `VITE_API_BASE_URL`).
-   **Build Process**: O comando `pnpm build` irá construir tanto o frontend quanto o backend. Para o Render, você pode usar `pnpm install` como build command e `pnpm start` como start command, ou configurar serviços separados para frontend e backend.
-   **Banco de Dados**: Para deploy, é altamente recomendado usar um serviço de banco de dados gerenciado (como o MySQL do Railway) e configurar a `DATABASE_URL` apropriadamente.

## Contribuição

Sinta-se à vontade para contribuir com melhorias, correções de bugs ou novas funcionalidades.

## Licença

Este projeto está licenciado sob a MIT License.

## Autor

Desenvolvido pela **Manus AI** com suporte profissional.
