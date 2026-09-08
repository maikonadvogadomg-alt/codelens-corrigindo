# PLANO DO PROJETO: Node.js API

> Gerado automaticamente pelo SK Code Editor em 08/09/2026, 14:19:54
> **160 arquivo(s)** | **~24.116 linhas de codigo**

---

## RESUMO EXECUTIVO

- **Tipo de aplicacao:** Full-Stack (React + Express)
- **Frontend / Stack principal:** React + Vite, TypeScript, Tailwind CSS
- **Backend / Dados:** Node.js + Express, Drizzle ORM
- **Versao:** 1.0.0

**Para rodar o projeto:**
```bash
npm install && npm run dev
```

---

## ESTRUTURA DE ARQUIVOS

```
Node.js API/
├── api/
│   └── index.ts
├── electron/
│   ├── main.js
│   └── preload.js
├── lib/
│   ├── api-client-react/
│   │   ├── generated/
│   │   │   ├── api.schemas.ts
│   │   │   └── api.ts
│   │   ├── custom-fetch.ts
│   │   └── index.ts
│   ├── api-zod/
│   │   ├── types/
│   │   │   ├── aiAnalysisResult.ts
│   │   │   ├── aiChatRequest.ts
│   │   │   ├── aiChatResponse.ts
│   │   │   ├── analyzeFileRequest.ts
│   │   │   ├── analyzeFolderRequest.ts
│   │   │   ├── chatMessage.ts
│   │   │   ├── chatMessageRole.ts
│   │   │   ├── createGithubRepoRequest.ts
│   │   │   ├── createGithubRepoResult.ts
│   │   │   ├── deleteFileParams.ts
│   │   │   ├── errorResponse.ts
│   │   │   ├── execCommandRequest.ts
│   │   │   ├── execCommandResponse.ts
│   │   │   ├── fileContent.ts
│   │   │   ├── fileNode.ts
│   │   │   ├── fileNodeType.ts
│   │   │   ├── getFileContentParams.ts
│   │   │   ├── healthStatus.ts
│   │   │   ├── importGithubRequest.ts
│   │   │   ├── index.ts
│   │   │   ├── project.ts
│   │   │   ├── projectDetail.ts
│   │   │   ├── settings.ts
│   │   │   ├── updateSettingsRequest.ts
│   │   │   ├── uploadProjectBody.ts
│   │   │   ├── writeFileRequest.ts
│   │   │   └── writeFileResponse.ts
│   │   ├── api.ts
│   │   └── index.ts
│   └── db/
│       ├── schema/
│       │   ├── index.ts
│       │   ├── playground.ts
│       │   ├── projects.ts
│       │   └── settings.ts
│       └── index.ts
├── public/
│   ├── favicon.svg
│   ├── manifest.json
│   └── sw.js
├── server/
│   ├── lib/
│   │   ├── devServerRegistry.ts
│   │   ├── logger.ts
│   │   ├── persistFiles.ts
│   │   └── storage.ts
│   ├── routes/
│   │   ├── ai.ts
│   │   ├── dev-server.ts
│   │   ├── exec.ts
│   │   ├── files.ts
│   │   ├── github.ts
│   │   ├── health.ts
│   │   ├── import-github.ts
│   │   ├── index.ts
│   │   ├── playground.ts
│   │   ├── preview.ts
│   │   ├── projects.ts
│   │   └── settings.ts
│   └── app.ts
├── src/
│   ├── components/
│   │   ├── ui/
│   │   │   ├── accordion.tsx
│   │   │   ├── alert-dialog.tsx
│   │   │   ├── alert.tsx
│   │   │   ├── aspect-ratio.tsx
│   │   │   ├── avatar.tsx
│   │   │   ├── badge.tsx
│   │   │   ├── breadcrumb.tsx
│   │   │   ├── button-group.tsx
│   │   │   ├── button.tsx
│   │   │   ├── calendar.tsx
│   │   │   ├── card.tsx
│   │   │   ├── carousel.tsx
│   │   │   ├── chart.tsx
│   │   │   ├── checkbox.tsx
│   │   │   ├── collapsible.tsx
│   │   │   ├── command.tsx
│   │   │   ├── context-menu.tsx
│   │   │   ├── dialog.tsx
│   │   │   ├── drawer.tsx
│   │   │   ├── dropdown-menu.tsx
│   │   │   ├── empty.tsx
│   │   │   ├── field.tsx
│   │   │   ├── form.tsx
│   │   │   ├── hover-card.tsx
│   │   │   ├── input-group.tsx
│   │   │   ├── input-otp.tsx
│   │   │   ├── input.tsx
│   │   │   ├── item.tsx
│   │   │   ├── kbd.tsx
│   │   │   ├── label.tsx
│   │   │   ├── menubar.tsx
│   │   │   ├── navigation-menu.tsx
│   │   │   ├── pagination.tsx
│   │   │   ├── popover.tsx
│   │   │   ├── progress.tsx
│   │   │   ├── radio-group.tsx
│   │   │   ├── resizable.tsx
│   │   │   ├── scroll-area.tsx
│   │   │   ├── select.tsx
│   │   │   ├── separator.tsx
│   │   │   ├── sheet.tsx
│   │   │   ├── sidebar.tsx
│   │   │   ├── skeleton.tsx
│   │   │   ├── slider.tsx
│   │   │   ├── sonner.tsx
│   │   │   ├── spinner.tsx
│   │   │   ├── switch.tsx
│   │   │   ├── table.tsx
│   │   │   ├── tabs.tsx
│   │   │   ├── textarea.tsx
│   │   │   ├── toast.tsx
│   │   │   ├── toaster.tsx
│   │   │   ├── toggle-group.tsx
│   │   │   ├── toggle.tsx
│   │   │   └── tooltip.tsx
│   │   ├── ai-panel.tsx
│   │   ├── code-viewer.tsx
│   │   ├── file-tree.tsx
│   │   ├── github-deploy-modal.tsx
│   │   ├── layout.tsx
│   │   ├── packages-panel.tsx
│   │   ├── preview-panel.tsx
│   │   ├── terminal-panel.tsx
│   │   └── theme-provider.tsx
│   ├── hooks/
│   │   ├── use-file-ops.ts
│   │   ├── use-mobile.tsx
│   │   └── use-toast.ts
│   ├── lib/
│   │   └── utils.ts
│   ├── lib-api-client/
│   │   ├── generated/
│   │   │   ├── api.schemas.ts
│   │   │   └── api.ts
│   │   ├── custom-fetch.ts
│   │   └── index.ts
│   ├── pages/
│   │   ├── chat.tsx
│   │   ├── home.tsx
│   │   ├── not-found.tsx
│   │   ├── playground.tsx
│   │   ├── project-explorer.tsx
│   │   └── settings.tsx
│   ├── App.tsx
│   ├── index.css
│   └── main.tsx
├── .env
├── backup-2026-06-27.sql
├── COMO-RODAR.md
├── COMO-USAR.txt
├── components.json
├── DOC_PROJETO.md
├── electron-builder.yml
├── index.html
├── INSTALACAO_LOCAL.md
├── package (2).json
├── package.json
├── PLANO.md
├── README-ELECTRON.md
├── README.md
├── server.js
├── server.ts
├── tsconfig.json
└── vite.config.ts
```

---

## STACK TECNOLOGICO DETECTADO

- **Frontend:** React + Vite, TypeScript, Tailwind CSS
- **Backend:** Node.js + Express, Drizzle ORM
- **Todos os pacotes (84):** @google/genai, @hookform/resolvers, @octokit/rest, @radix-ui/react-accordion, @radix-ui/react-alert-dialog, @radix-ui/react-aspect-ratio, @radix-ui/react-avatar, @radix-ui/react-checkbox, @radix-ui/react-collapsible, @radix-ui/react-context-menu, @radix-ui/react-dialog, @radix-ui/react-dropdown-menu, @radix-ui/react-hover-card, @radix-ui/react-label, @radix-ui/react-menubar, @radix-ui/react-navigation-menu, @radix-ui/react-popover, @radix-ui/react-progress, @radix-ui/react-radio-group, @radix-ui/react-scroll-area, @radix-ui/react-select, @radix-ui/react-separator, @radix-ui/react-slider, @radix-ui/react-slot, @radix-ui/react-switch, @radix-ui/react-tabs, @radix-ui/react-toast, @radix-ui/react-toggle, @radix-ui/react-toggle-group, @radix-ui/react-tooltip, @tailwindcss/typography, @tailwindcss/vite, @tanstack/react-query, @types/adm-zip, @types/mime-types, @types/multer, @vitejs/plugin-react, adm-zip, class-variance-authority, clsx, cmdk, cookie-parser, cors, date-fns, embla-carousel-react, express, framer-motion, highlight.js, input-otp, lucide-react, mime-types, multer, next-themes, pino, pino-http, react, react-day-picker, react-dom, react-hook-form, react-icons, react-markdown, react-resizable-panels, recharts, rehype-highlight, remark-gfm, sonner, tailwind-merge, tailwindcss, tw-animate-css, vaul, vite, wouter, zod, @libsql/client, drizzle-orm, @types/cookie-parser, @types/cors, @types/express, @types/node, @types/react, @types/react-dom, tsx, electron, electron-builder

---

## ROTAS DA API (endpoints detectados automaticamente)

```
USE    /api  (em server/app.ts)
POST   /ai/chat  (em server/routes/ai.ts)
POST   /ai/analyze-file  (em server/routes/ai.ts)
POST   /ai/analyze-folder  (em server/routes/ai.ts)
POST   /ai/tts  (em server/routes/ai.ts)
POST   /projects/:projectId/dev-server/start  (em server/routes/dev-server.ts)
DELETE /projects/:projectId/dev-server/stop  (em server/routes/dev-server.ts)
GET    /projects/:projectId/dev-server/status  (em server/routes/dev-server.ts)
POST   /projects/:projectId/exec-stream  (em server/routes/exec.ts)
POST   /projects/:projectId/exec  (em server/routes/exec.ts)
GET    /projects/:projectId/files  (em server/routes/files.ts)
PUT    /projects/:projectId/files  (em server/routes/files.ts)
DELETE /projects/:projectId/files  (em server/routes/files.ts)
POST   /projects/:projectId/files/mkdir  (em server/routes/files.ts)
PATCH  /projects/:projectId/files  (em server/routes/files.ts)
POST   /projects/:projectId/files/copy  (em server/routes/files.ts)
POST   /github/create-repo  (em server/routes/github.ts)
GET    /healthz  (em server/routes/health.ts)
POST   /projects/import-github  (em server/routes/import-github.ts)
GET    /playground  (em server/routes/playground.ts)
GET    /playground/:id  (em server/routes/playground.ts)
POST   /playground  (em server/routes/playground.ts)
PUT    /playground/:id  (em server/routes/playground.ts)
DELETE /playground/:id  (em server/routes/playground.ts)
GET    /projects/:projectId/preview/status  (em server/routes/preview.ts)
GET    /projects/:projectId/preview/*path  (em server/routes/preview.ts)
GET    /projects  (em server/routes/projects.ts)
POST   /projects  (em server/routes/projects.ts)
GET    /api/hello  (em server/routes/projects.ts)
POST   /projects/blank  (em server/routes/projects.ts)
GET    /projects/:projectId  (em server/routes/projects.ts)
GET    /projects/:projectId/export  (em server/routes/projects.ts)
DELETE /projects/:projectId  (em server/routes/projects.ts)
GET    /settings  (em server/routes/settings.ts)
PUT    /settings  (em server/routes/settings.ts)
```

---

## SCRIPTS DISPONIVEIS (package.json)

```bash
npm run dev           # npx tsx server.ts
npm run start         # npx tsx server.ts
npm run build         # vite build
npm run preview       # vite preview
npm run electron:dev  # electron electron/main.js
npm run electron:build  # vite build && electron-builder
```

---

## VARIAVEIS DE AMBIENTE NECESSARIAS

Crie um arquivo `.env` na raiz com estas variaveis:

```env
DATABASE_PATH=seu_valor_aqui
PORT=seu_valor_aqui
STORAGE_PATH=seu_valor_aqui
AI_INTEGRATIONS_GEMINI_BASE_URL=seu_valor_aqui
AI_INTEGRATIONS_GEMINI_API_KEY=seu_valor_aqui
PATH=seu_valor_aqui
```

---

## ARQUIVOS PRINCIPAIS

- `api/index.ts` — Arquivo principal
- `index.html` — Pagina HTML principal
- `lib/api-client-react/index.ts` — Arquivo principal
- `lib/api-zod/index.ts` — Arquivo principal
- `lib/api-zod/types/index.ts` — Arquivo principal
- `lib/db/index.ts` — Arquivo principal
- `lib/db/schema/index.ts` — Arquivo principal
- `server.js` — Ponto de entrada do backend
- `server.ts` — Ponto de entrada do backend
- `server/app.ts` — Ponto de entrada do backend

---

## GUIA COMPLETO — O QUE CADA PARTE DO PROJETO FAZ

> Esta secao explica, em linguagem simples, o que e para que serve cada pasta e cada arquivo.

### 📁 Raiz do Projeto (pasta principal)
> Arquivos de configuracao e pontos de entrada ficam aqui.

**`.env`** _(2 linhas)_
Arquivo de variaveis secretas (senhas, chaves de API). NUNCA suba este arquivo para o GitHub.

**`COMO-RODAR.md`** _(81 linhas)_
Arquivo de documentacao em Markdown (texto formatado com #titulos, **negrito**, listas).

**`COMO-USAR.txt`** _(59 linhas)_
Arquivo TXT — parte do projeto.

**`DOC_PROJETO.md`** _(335 linhas)_
Arquivo de documentacao em Markdown (texto formatado com #titulos, **negrito**, listas).

**`INSTALACAO_LOCAL.md`** _(199 linhas)_
Arquivo de documentacao em Markdown (texto formatado com #titulos, **negrito**, listas).

**`PLANO.md`** _(975 linhas)_
Este documento! Gerado automaticamente pelo SK Code Editor com toda a estrutura do projeto.

**`README-ELECTRON.md`** _(22 linhas)_
Arquivo de documentacao em Markdown (texto formatado com #titulos, **negrito**, listas).

**`README.md`** _(25 linhas)_
Documentacao principal do projeto. Explica o que o projeto faz e como rodar.

**`backup-2026-06-27.sql`** _(10 linhas)_
Script SQL — contem comandos para criar tabelas, inserir ou consultar dados no banco.

**`components.json`** _(20 linhas)_
Arquivo de dados ou configuracao no formato JSON (chave: valor).

**`electron-builder.yml`** _(29 linhas)_
Arquivo YML — parte do projeto.

**`index.html`** _(24 linhas)_
Pagina HTML raiz do projeto. E o ponto de entrada que o browser carrega primeiro.

**`package (2).json`** _(13 linhas)_
Arquivo de dados ou configuracao no formato JSON (chave: valor).

**`package.json`** _(103 linhas)_
Registro de dependencias e scripts do projeto. Aqui ficam os comandos (npm run dev, npm start) e os pacotes instalados.

**`server.js`** _(86 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`server.ts`** _(38 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`tsconfig.json`** _(23 linhas)_
Configuracao do TypeScript. Diz para o computador como interpretar o codigo .ts e .tsx.

**`vite.config.ts`** _(21 linhas)_
Configuracao do Vite (servidor de desenvolvimento). Define a porta, alias de caminhos e plugins usados.

---

### 📁 `api/`
> Comunicacao com servidor, banco de dados ou APIs externas.

**`index.ts`** _(4 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

---

### 📁 `electron/`
> Pasta 'electron' — agrupamento de arquivos relacionados.

**`main.js`** _(115 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`preload.js`** _(7 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `public/`
> Arquivos estaticos: imagens, icones, fontes, arquivos publicos.

**`favicon.svg`** _(4 linhas)_
Imagem vetorial (icone ou ilustracao que nao perde qualidade ao ampliar).

**`manifest.json`** _(27 linhas)_
Manifesto do PWA — define nome, icone e configuracoes para instalar o app no celular.

**`sw.js`** _(48 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `server/`
> Pasta 'server' — agrupamento de arquivos relacionados.

**`app.ts`** _(14 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `src/`
> Codigo-fonte principal do projeto. Nao apague esta pasta.

**`App.tsx`** _(44 linhas)_
Componente RAIZ do frontend — e o pai de todos os outros componentes. Aqui ficam as rotas principais.

**`index.css`** _(386 linhas)_
Arquivo de estilos visuais — cores, tamanhos, fontes, espacamentos da interface.

**`main.tsx`** _(12 linhas)_
Ponto de entrada do React — monta o componente App na pagina HTML.

---

### 📁 `lib/api-client-react/`
> Pasta 'api-client-react' — agrupamento de arquivos relacionados.

**`custom-fetch.ts`** _(372 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`index.ts`** _(5 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

---

### 📁 `lib/api-zod/`
> Pasta 'api-zod' — agrupamento de arquivos relacionados.

**`api.ts`** _(257 linhas)_
Arquivo de SERVICO/API — funcoes para comunicar com o servidor ou API externa.

**`index.ts`** _(3 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

---

### 📁 `lib/db/`
> Pasta 'db' — agrupamento de arquivos relacionados.

**`index.ts`** _(65 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

---

### 📁 `server/lib/`
> Funcoes auxiliares reutilizaveis em varios lugares do projeto.

**`devServerRegistry.ts`** _(345 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`logger.ts`** _(9 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`persistFiles.ts`** _(143 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`storage.ts`** _(161 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `server/routes/`
> Definicao das URLs e navegacao do app.

**`ai.ts`** _(712 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`dev-server.ts`** _(231 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`exec.ts`** _(354 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`files.ts`** _(184 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`github.ts`** _(171 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`health.ts`** _(12 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`import-github.ts`** _(169 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`index.ts`** _(29 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

**`playground.ts`** _(77 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`preview.ts`** _(141 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`projects.ts`** _(527 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`settings.ts`** _(78 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `src/components/`
> Pecas visuais reutilizaveis da interface (botoes, cards, formularios...).

**`ai-panel.tsx`** _(1176 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`code-viewer.tsx`** _(343 linhas)_
Componente de PAGINA/TELA — representa uma tela completa navegavel no app.

**`file-tree.tsx`** _(389 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`github-deploy-modal.tsx`** _(626 linhas)_
Componente MODAL — janela/popup que aparece sobre a tela pedindo uma acao ou mostrando uma informacao importante.

**`layout.tsx`** _(72 linhas)_
Componente de LAYOUT — define a estrutura visual da pagina (cabecalho, sidebar, rodape). Envolve outros componentes.

**`packages-panel.tsx`** _(537 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`preview-panel.tsx`** _(586 linhas)_
Componente de PAGINA/TELA — representa uma tela completa navegavel no app.

**`terminal-panel.tsx`** _(511 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`theme-provider.tsx`** _(72 linhas)_
Componente PROVIDER — 'fornece' dados/funcoes para todos os componentes filhos via Context API do React.

---

### 📁 `src/hooks/`
> Hooks React customizados — logica reutilizavel de estado e efeitos.

**`use-file-ops.ts`** _(110 linhas)_
HOOK React personalizado para gerenciar estado/comportamento de '-file-ops'.

**`use-mobile.tsx`** _(20 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`use-toast.ts`** _(192 linhas)_
HOOK React personalizado para gerenciar estado/comportamento de '-toast'.

---

### 📁 `src/lib/`
> Funcoes auxiliares reutilizaveis em varios lugares do projeto.

**`utils.ts`** _(16 linhas)_
Funcoes UTILITARIAS — ferramentas reutilizaveis de uso geral no projeto.

---

### 📁 `src/lib-api-client/`
> Pasta 'lib-api-client' — agrupamento de arquivos relacionados.

**`custom-fetch.ts`** _(372 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`index.ts`** _(5 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

---

### 📁 `src/pages/`
> Telas completas do app — cada arquivo aqui e uma pagina navegavel.

**`chat.tsx`** _(485 linhas)_
Componente de CHAT/MENSAGENS — interface de conversa em tempo real.

**`home.tsx`** _(609 linhas)_
Componente HOME — pagina/tela inicial do app.

**`not-found.tsx`** _(22 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`playground.tsx`** _(244 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`project-explorer.tsx`** _(666 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`settings.tsx`** _(665 linhas)_
Componente de CONFIGURACOES — tela onde o usuario ajusta preferencias do app.

---

### 📁 `lib/api-client-react/generated/`
> Pasta 'generated' — agrupamento de arquivos relacionados.

**`api.schemas.ts`** _(205 linhas)_
Arquivo de SERVICO/API — funcoes para comunicar com o servidor ou API externa.

**`api.ts`** _(1444 linhas)_
Arquivo de SERVICO/API — funcoes para comunicar com o servidor ou API externa.

---

### 📁 `lib/api-zod/types/`
> Definicoes de tipos TypeScript — contratos de dados.

**`aiAnalysisResult.ts`** _(13 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`aiChatRequest.ts`** _(38 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`aiChatResponse.ts`** _(13 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`analyzeFileRequest.ts`** _(14 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`analyzeFolderRequest.ts`** _(13 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`chatMessage.ts`** _(14 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`chatMessageRole.ts`** _(16 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`createGithubRepoRequest.ts`** _(16 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`createGithubRepoResult.ts`** _(14 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`deleteFileParams.ts`** _(12 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`errorResponse.ts`** _(12 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`execCommandRequest.ts`** _(18 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`execCommandResponse.ts`** _(15 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`fileContent.ts`** _(15 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`fileNode.ts`** _(16 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`fileNodeType.ts`** _(15 linhas)_
Arquivo de TIPOS — define as estruturas de dados (interfaces TypeScript) usadas no projeto.

**`getFileContentParams.ts`** _(15 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`healthStatus.ts`** _(12 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`importGithubRequest.ts`** _(18 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`index.ts`** _(35 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

**`project.ts`** _(16 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`projectDetail.ts`** _(18 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`settings.ts`** _(17 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`updateSettingsRequest.ts`** _(19 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`uploadProjectBody.ts`** _(13 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`writeFileRequest.ts`** _(15 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`writeFileResponse.ts`** _(13 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `lib/db/schema/`
> Pasta 'schema' — agrupamento de arquivos relacionados.

**`index.ts`** _(4 linhas)_
Arquivo INDEX — ponto de entrada da pasta, exporta tudo que esta dentro.

**`playground.ts`** _(12 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`projects.ts`** _(29 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

**`settings.ts`** _(18 linhas)_
Arquivo TypeScript/JavaScript — logica, funcoes ou modulo do projeto.

---

### 📁 `src/components/ui/`
> Componentes de UI (interface) basicos e genericos.

**`accordion.tsx`** _(56 linhas)_
Componente ACCORDION — secoes que abrem/fecham ao clicar, economizando espaco na tela.

**`alert-dialog.tsx`** _(140 linhas)_
Componente de NOTIFICACAO/ALERTA — mensagem temporaria que aparece na tela (ex: 'Salvo com sucesso!').

**`alert.tsx`** _(60 linhas)_
Componente de NOTIFICACAO/ALERTA — mensagem temporaria que aparece na tela (ex: 'Salvo com sucesso!').

**`aspect-ratio.tsx`** _(6 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`avatar.tsx`** _(51 linhas)_
Componente AVATAR — foto ou iniciais do usuario em formato circular.

**`badge.tsx`** _(44 linhas)_
Componente BADGE (etiqueta) — pequeno indicador com numero ou status (ex: '3 novas mensagens').

**`breadcrumb.tsx`** _(116 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`button-group.tsx`** _(84 linhas)_
Componente de BOTAO — elemento clicavel reutilizavel com estilo padrao do projeto.

**`button.tsx`** _(66 linhas)_
Componente de BOTAO — elemento clicavel reutilizavel com estilo padrao do projeto.

**`calendar.tsx`** _(214 linhas)_
Componente CALENDARIO/AGENDA — visualizacao e selecao de datas e eventos.

**`card.tsx`** _(77 linhas)_
Componente CARD (cartao) — exibe uma informacao em um bloco visual com borda e sombra. Muito usado para listas de items.

**`carousel.tsx`** _(261 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`chart.tsx`** _(368 linhas)_
Componente de GRAFICO — visualizacao de dados em forma de grafico (barras, linhas, pizza...).

**`checkbox.tsx`** _(29 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`collapsible.tsx`** _(12 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`command.tsx`** _(154 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`context-menu.tsx`** _(199 linhas)_
CONTEXT do React — mecanismo para compartilhar dados entre componentes sem passar por props.

**`dialog.tsx`** _(121 linhas)_
Componente DIALOG — caixa de dialogo que exige resposta do usuario (confirmar, cancelar...).

**`drawer.tsx`** _(117 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`dropdown-menu.tsx`** _(202 linhas)_
Componente de MENU/DROPDOWN — lista de opcoes que aparece ao clicar em um botao.

**`empty.tsx`** _(105 linhas)_
Componente de ESTADO VAZIO — exibido quando nao ha dados para mostrar (ex: 'Nenhum resultado encontrado').

**`field.tsx`** _(245 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`form.tsx`** _(177 linhas)_
Componente de FORMULARIO — campos de entrada de dados (texto, selecao, etc.) com validacao.

**`hover-card.tsx`** _(28 linhas)_
Componente CARD (cartao) — exibe uma informacao em um bloco visual com borda e sombra. Muito usado para listas de items.

**`input-group.tsx`** _(169 linhas)_
Componente de CAMPO DE ENTRADA — elemento de input com estilo personalizado.

**`input-otp.tsx`** _(70 linhas)_
Componente de CAMPO DE ENTRADA — elemento de input com estilo personalizado.

**`input.tsx`** _(23 linhas)_
Componente de CAMPO DE ENTRADA — elemento de input com estilo personalizado.

**`item.tsx`** _(194 linhas)_
Componente de ITEM — representa um elemento individual dentro de uma lista ou colecao.

**`kbd.tsx`** _(29 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`label.tsx`** _(27 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`menubar.tsx`** _(255 linhas)_
Componente de MENU/DROPDOWN — lista de opcoes que aparece ao clicar em um botao.

**`navigation-menu.tsx`** _(129 linhas)_
Componente de NAVEGACAO/CABECALHO — barra superior com logo, menu e links de navegacao.

**`pagination.tsx`** _(118 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`popover.tsx`** _(32 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`progress.tsx`** _(29 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`radio-group.tsx`** _(43 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`resizable.tsx`** _(46 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`scroll-area.tsx`** _(47 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`select.tsx`** _(160 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`separator.tsx`** _(30 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`sheet.tsx`** _(141 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`sidebar.tsx`** _(728 linhas)_
Componente de BARRA LATERAL — menu ou painel que aparece na lateral da tela.

**`skeleton.tsx`** _(16 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`slider.tsx`** _(27 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`sonner.tsx`** _(32 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`spinner.tsx`** _(17 linhas)_
Componente de CARREGAMENTO — animacao visual que aparece enquanto dados estao sendo buscados.

**`switch.tsx`** _(28 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`table.tsx`** _(121 linhas)_
Componente de TABELA — exibe dados em linhas e colunas.

**`tabs.tsx`** _(54 linhas)_
Componente de ABAS — permite alternar entre diferentes secoes de conteudo com clique.

**`textarea.tsx`** _(23 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`toast.tsx`** _(128 linhas)_
Componente de NOTIFICACAO/ALERTA — mensagem temporaria que aparece na tela (ex: 'Salvo com sucesso!').

**`toaster.tsx`** _(34 linhas)_
Componente de NOTIFICACAO/ALERTA — mensagem temporaria que aparece na tela (ex: 'Salvo com sucesso!').

**`toggle-group.tsx`** _(62 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`toggle.tsx`** _(44 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

**`tooltip.tsx`** _(33 linhas)_
Componente React — parte visual reutilizavel da interface do usuario.

---

### 📁 `src/lib-api-client/generated/`
> Pasta 'generated' — agrupamento de arquivos relacionados.

**`api.schemas.ts`** _(205 linhas)_
Arquivo de SERVICO/API — funcoes para comunicar com o servidor ou API externa.

**`api.ts`** _(1444 linhas)_
Arquivo de SERVICO/API — funcoes para comunicar com o servidor ou API externa.

---

## CONTEXTO PARA IA (copie e cole para continuar o projeto)

> Use este bloco para explicar o projeto para qualquer IA ou desenvolvedor:

```
Projeto: Node.js API
Tipo: Full-Stack (React + Express)
Stack: React + Vite, TypeScript, Tailwind CSS, Node.js + Express, Drizzle ORM
Arquivos: 160 | Linhas: ~24.116
Rotas API: 35 endpoint(s) detectado(s)
Variaveis de ambiente necessarias: DATABASE_PATH, PORT, STORAGE_PATH, AI_INTEGRATIONS_GEMINI_BASE_URL, AI_INTEGRATIONS_GEMINI_API_KEY, PATH

Estrutura principal:
  .env
  COMO-RODAR.md
  COMO-USAR.txt
  DOC_PROJETO.md
  INSTALACAO_LOCAL.md
  PLANO.md
  README-ELECTRON.md
  README.md
  api/index.ts
  backup-2026-06-27.sql
  components.json
  electron-builder.yml
  electron/main.js
  electron/preload.js
  index.html
  lib/api-client-react/custom-fetch.ts
  lib/api-client-react/generated/api.schemas.ts
  lib/api-client-react/generated/api.ts
  lib/api-client-react/index.ts
  lib/api-zod/api.ts
  lib/api-zod/index.ts
  lib/api-zod/types/aiAnalysisResult.ts
  lib/api-zod/types/aiChatRequest.ts
  lib/api-zod/types/aiChatResponse.ts
  lib/api-zod/types/analyzeFileRequest.ts
  lib/api-zod/types/analyzeFolderRequest.ts
  lib/api-zod/types/chatMessage.ts
  lib/api-zod/types/chatMessageRole.ts
  lib/api-zod/types/createGithubRepoRequest.ts
  lib/api-zod/types/createGithubRepoResult.ts
  lib/api-zod/types/deleteFileParams.ts
  lib/api-zod/types/errorResponse.ts
  lib/api-zod/types/execCommandRequest.ts
  lib/api-zod/types/execCommandResponse.ts
  lib/api-zod/types/fileContent.ts
  lib/api-zod/types/fileNode.ts
  lib/api-zod/types/fileNodeType.ts
  lib/api-zod/types/getFileContentParams.ts
  lib/api-zod/types/healthStatus.ts
  lib/api-zod/types/importGithubRequest.ts
  lib/api-zod/types/index.ts
  lib/api-zod/types/project.ts
  lib/api-zod/types/projectDetail.ts
  lib/api-zod/types/settings.ts
  lib/api-zod/types/updateSettingsRequest.ts
  lib/api-zod/types/uploadProjectBody.ts
  lib/api-zod/types/writeFileRequest.ts
  lib/api-zod/types/writeFileResponse.ts
  lib/db/index.ts
  lib/db/schema/index.ts
  lib/db/schema/playground.ts
  lib/db/schema/projects.ts
  lib/db/schema/settings.ts
  package (2).json
  package.json
  public/favicon.svg
  public/manifest.json
  public/sw.js
  server.js
  server.ts
  server/app.ts
  server/lib/devServerRegistry.ts
  server/lib/logger.ts
  server/lib/persistFiles.ts
  server/lib/storage.ts
  server/routes/ai.ts
  server/routes/dev-server.ts
  server/routes/exec.ts
  server/routes/files.ts
  server/routes/github.ts
  server/routes/health.ts
  server/routes/import-github.ts
  server/routes/index.ts
  server/routes/playground.ts
  server/routes/preview.ts
  server/routes/projects.ts
  server/routes/settings.ts
  src/App.tsx
  src/components/ai-panel.tsx
  src/components/code-viewer.tsx
  src/components/file-tree.tsx
  src/components/github-deploy-modal.tsx
  src/components/layout.tsx
  src/components/packages-panel.tsx
  src/components/preview-panel.tsx
  src/components/terminal-panel.tsx
  src/components/theme-provider.tsx
  src/components/ui/accordion.tsx
  src/components/ui/alert-dialog.tsx
  src/components/ui/alert.tsx
  src/components/ui/aspect-ratio.tsx
  src/components/ui/avatar.tsx
  src/components/ui/badge.tsx
  src/components/ui/breadcrumb.tsx
  src/components/ui/button-group.tsx
  src/components/ui/button.tsx
  src/components/ui/calendar.tsx
  src/components/ui/card.tsx
  src/components/ui/carousel.tsx
  src/components/ui/chart.tsx
  src/components/ui/checkbox.tsx
  src/components/ui/collapsible.tsx
  src/components/ui/command.tsx
  src/components/ui/context-menu.tsx
  src/components/ui/dialog.tsx
  src/components/ui/drawer.tsx
  src/components/ui/dropdown-menu.tsx
  src/components/ui/empty.tsx
  src/components/ui/field.tsx
  src/components/ui/form.tsx
  src/components/ui/hover-card.tsx
  src/components/ui/input-group.tsx
  src/components/ui/input-otp.tsx
  src/components/ui/input.tsx
  src/components/ui/item.tsx
  src/components/ui/kbd.tsx
  src/components/ui/label.tsx
  src/components/ui/menubar.tsx
  src/components/ui/navigation-menu.tsx
  src/components/ui/pagination.tsx
  src/components/ui/popover.tsx
  src/components/ui/progress.tsx
  src/components/ui/radio-group.tsx
  src/components/ui/resizable.tsx
  src/components/ui/scroll-area.tsx
  src/components/ui/select.tsx
  src/components/ui/separator.tsx
  src/components/ui/sheet.tsx
  src/components/ui/sidebar.tsx
  src/components/ui/skeleton.tsx
  src/components/ui/slider.tsx
  src/components/ui/sonner.tsx
  src/components/ui/spinner.tsx
  src/components/ui/switch.tsx
  src/components/ui/table.tsx
  src/components/ui/tabs.tsx
  src/components/ui/textarea.tsx
  src/components/ui/toast.tsx
  src/components/ui/toaster.tsx
  src/components/ui/toggle-group.tsx
  src/components/ui/toggle.tsx
  src/components/ui/tooltip.tsx
  src/hooks/use-file-ops.ts
  src/hooks/use-mobile.tsx
  src/hooks/use-toast.ts
  src/index.css
  src/lib-api-client/custom-fetch.ts
  src/lib-api-client/generated/api.schemas.ts
  src/lib-api-client/generated/api.ts
  src/lib-api-client/index.ts
  src/lib/utils.ts
  src/main.tsx
  src/pages/chat.tsx
  src/pages/home.tsx
  src/pages/not-found.tsx
  src/pages/playground.tsx
  src/pages/project-explorer.tsx
  src/pages/settings.tsx
  tsconfig.json
  vite.config.ts
```

---

*Plano gerado pelo SK Code Editor — 08/09/2026, 14:19:54*