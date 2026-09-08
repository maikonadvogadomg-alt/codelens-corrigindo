# CodeLens Local — Como Rodar e Gerar Executável

## Pré-requisitos (instale uma vez só)
- **Node.js LTS** → https://nodejs.org

---

## Opção 1: Rodar direto no navegador (mais simples)

```bash
# No terminal, dentro da pasta do projeto:
npm install
npm run dev

# Depois abra: http://localhost:5000
```

---

## Opção 2: Abrir como app Electron (janela própria, sem navegador)

```bash
npm install
npm run electron:dev
```

---

## Opção 3: Gerar o executável .exe (Windows)

```bash
npm install
npm run electron:build
```

O instalador `.exe` estará na pasta `dist-electron/`.

---

## Configurar a IA

Dentro do app:
1. Clique em **Configurações** (ícone de engrenagem)
2. Cole sua chave de API
3. Escolha o modelo

| Provedor | Chave começa com |
|----------|-----------------|
| Claude (Anthropic) | `sk-ant-...` |
| Gemini (Google) | `AIza...` |
| Groq | `gsk_...` |
| OpenAI | `sk-...` |

---

## Banco de dados (SQLite — local, sem internet)

- Os dados ficam salvos automaticamente no seu computador
- **Windows:** `C:\Users\SeuNome\AppData\Roaming\CodeLens\codelens.db`
- **Mac:** `~/Library/Application Support/CodeLens/codelens.db`
- Não precisa de Neon, PostgreSQL ou internet para funcionar

---

## Playground HTML

- Acesse pelo menu lateral (ícone de arquivo de código)
- Escreva HTML/CSS/JS e veja o resultado ao vivo
- Salve quantos arquivos quiser — ficam no banco local
- Botão **Baixar .html** para exportar o arquivo

---

## Problemas comuns

| Erro | Solução |
|------|---------|
| Porta 5000 em uso | Mude `PORT=5001` no arquivo `.env` |
| `npm install` falha | Certifique-se de ter Node.js 18+ instalado |
| App não abre | Tente `npm run dev` primeiro para ver o erro |
