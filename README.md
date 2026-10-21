# 🦉 Tytos - aprendizado de idiomas

> Plataforma web de aprendizado de idiomas com lições curtas e gamificadas (vidas, XP, ranking e missões).

**Status:** 🚧 em desenvolvimento. O código-fonte já está neste repositório e roda localmente seguindo o passo a passo abaixo.

![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4?logo=tailwindcss&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Neon-4169E1?logo=postgresql&logoColor=white)

---

## 📖 Sobre o projeto

O Tytos é um projeto de estudo de desenvolvimento full-stack. A ideia é oferecer uma experiência de aprendizado de idiomas em **trilhas de lições**, com sistema de vidas, pontos de experiência (XP), ranking e missões.

> ⚠️ **Aviso:** este é um projeto independente e educacional. **Não possui qualquer relação, afiliação ou endosso de terceiros** que ofereçam serviços semelhantes. Todas as marcas citadas pertencem aos seus respectivos titulares.

---

## ✨ Funcionalidades

- 🗺️ Trilha de cursos, unidades e lições
- ❓ Desafios interativos com efeitos sonoros
- ❤️ Sistema de vidas
- 🌟 Pontos de experiência (XP)
- 🏆 Ranking
- 🎯 Missões por marcos de pontos
- 🛍️ Loja para trocar pontos por vidas
- 💳 Plano Pro com vidas ilimitadas (Stripe)
- 🔐 Autenticação de usuários (Clerk)
- 📊 Painel administrativo de conteúdo (`/admin`)
- 📱 Layout responsivo (mobile-first)

---

## 🛠 Tecnologias

| Camada | Tecnologia |
|---|---|
| Framework | [Next.js 14](https://nextjs.org/) |
| Interface | [React](https://react.dev/), [Tailwind CSS](https://tailwindcss.com/), [shadcn/ui](https://ui.shadcn.com/) |
| Linguagem | [TypeScript](https://www.typescriptlang.org/) |
| Banco de dados | [PostgreSQL](https://www.postgresql.org/) via [Neon](https://neon.tech/) |
| ORM | [Drizzle ORM](https://orm.drizzle.team/) |
| Autenticação | [Clerk](https://clerk.com/) |
| Pagamentos | [Stripe](https://stripe.com/) |
| Painel admin | [React Admin](https://marmelab.com/react-admin/) |
| Hospedagem | [Vercel](https://vercel.com/) |

---

## 🧰 Ferramentas que você precisa instalar

| Ferramenta | Para que serve | Download |
|---|---|---|
| **Node.js 20 LTS** (já inclui o `npm`) | Roda o projeto | <https://nodejs.org/> |
| **Git** | Baixa o código | <https://git-scm.com/downloads> |
| **VS Code** (recomendado) | Editor de código | <https://code.visualstudio.com/> |
| **Android Studio** (só para o app Android) | Emulador e build Android | <https://developer.android.com/studio> |

Contas gratuitas (crie antes de começar):

| Serviço | Para que serve | Link |
|---|---|---|
| **Clerk** | Login dos usuários | <https://clerk.com/> |
| **Neon** | Banco de dados PostgreSQL | <https://neon.tech/> |
| **Stripe** | Pagamentos do plano Pro (modo teste) | <https://dashboard.stripe.com/register> |

> Versão mínima do Node: **18.17**. Recomendado: **20 LTS**.

### Instalação rápida

**Windows**

1. Baixe e instale o Node.js (instalador `.msi`) e o Git nos links acima. Pode avançar com as opções padrão.
2. Feche e abra o **PowerShell** de novo.
3. Confira se funcionou:

```powershell
node -v
npm -v
git --version
```

Alternativa pelo terminal (Windows 10/11):

```powershell
winget install OpenJS.NodeJS.LTS
winget install Git.Git
```

**macOS**

1. Instale o [Homebrew](https://brew.sh/) (cole no Terminal o comando que aparece na página).
2. Instale as ferramentas:

```bash
brew install node git
```

3. Confira:

```bash
node -v
npm -v
git --version
```

(Se preferir, baixe os instaladores direto em <https://nodejs.org/> e <https://git-scm.com/downloads>.)

---

## 🚀 Como rodar no computador (Windows e macOS)

### 1. Baixar o projeto

```bash
git clone https://github.com/eduardogrigorio/tytos.com.br.git
cd tytos.com.br
npm install
```

### 2. Criar o banco de dados (Neon)

1. Entre em <https://neon.tech/> e crie um projeto.
2. Na tela do projeto, clique em **Connect** e copie a **connection string** (começa com `postgresql://`).

### 3. Configurar o login (Clerk)

1. Entre em <https://dashboard.clerk.com/> e crie uma aplicação.
2. Vá em **API Keys** e copie a `Publishable key` e a `Secret key`.

### 4. Criar o arquivo `.env.local`

Crie o arquivo na **raiz do projeto** (mesma pasta do `package.json`).

- **Windows (PowerShell):** `New-Item .env.local -ItemType File`
- **macOS:** `touch .env.local`

Abra no VS Code e cole (preenchendo com as suas chaves):

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="pk_test_..."
CLERK_SECRET_KEY="sk_test_..."
DATABASE_URL="postgresql://usuario:senha@host/banco?sslmode=require"
NEXT_PUBLIC_APP_URL="http://localhost:3000"
STRIPE_API_KEY="sk_test_..."
STRIPE_WEBHOOK_SECRET="whsec_..."
```

> 🔒 **Nunca** envie o `.env.local` ao GitHub. Ele já está no `.gitignore`.
>
> 💡 As chaves do Stripe só são necessárias para testar o plano Pro. Para ver o restante do app, valores de teste do painel do Stripe (<https://dashboard.stripe.com/test/apikeys>) bastam.

### 5. Criar as tabelas e popular o banco

```bash
npm run db:push
npm run db:seed
```

### 6. Iniciar o app

```bash
npm run dev
```

Abra <http://localhost:3000> no navegador. Para parar, pressione `Ctrl + C` no terminal.

### Comandos úteis

| Comando | O que faz |
|---|---|
| `npm run dev` | Inicia em modo desenvolvimento |
| `npm run build` | Gera a versão de produção |
| `npm run start` | Roda a versão de produção |
| `npm run lint` | Verifica problemas no código |
| `npm run db:push` | Cria/atualiza as tabelas no banco |
| `npm run db:seed` | Popula o banco com cursos e lições de exemplo |
| `npm run db:reset` | Limpa o banco |
| `npm run db:studio` | Abre o Drizzle Studio (visualizar o banco) |

---

## 🔑 Acessar o painel administrativo

O painel fica em <http://localhost:3000/admin> e só abre para os IDs listados em `lib/admin.ts`.

1. Entre no app e crie sua conta.
2. No painel do Clerk, abra **Users**, clique no seu usuário e copie o **User ID** (`user_...`).
3. Em `lib/admin.ts`, **substitua** o ID existente pelo seu:

```ts
const adminIds = [
  "user_SEU_ID_AQUI",
];
```

---

## 📱 Criar o primeiro app Android

O projeto é um site Next.js (com servidor e banco), então o app Android funciona como um **"casulo" que abre o site publicado**. Há dois caminhos, do mais simples ao mais completo.

### Opção A: instalar como PWA (mais fácil, sem Android Studio)

> Ainda depende de transformar o projeto em PWA (item do roadmap): adicionar `manifest.json` e ícones.

Depois de publicar o site (veja "Publicar online" abaixo), abra o endereço no Chrome do celular e use **⋮ → Adicionar à tela inicial**.

### Opção B: app Android com Capacitor + Android Studio

**Antes de começar:** publique o site na Vercel (próxima seção) e guarde o endereço, por exemplo `https://seu-app.vercel.app`.

**1. Instale o Android Studio** <https://developer.android.com/studio> (Windows e macOS). Na primeira abertura, deixe o assistente instalar o **Android SDK** e um **emulador**.

**2. Instale o Capacitor no projeto:**

```bash
npm install @capacitor/core
npm install -D @capacitor/cli
npm install @capacitor/android
npx cap init Tytos br.com.tytos --web-dir=public
```

**3. Edite o `capacitor.config.ts`** criado na raiz, apontando para o site publicado:

```ts
import type { CapacitorConfig } from "@capacitor/cli";

const config: CapacitorConfig = {
  appId: "br.com.tytos",
  appName: "Tytos",
  webDir: "public",
  server: {
    url: "https://seu-app.vercel.app",
  },
};

export default config;
```

**4. Crie o projeto Android e abra no Android Studio:**

```bash
npx cap add android
npx cap sync android
npx cap open android
```

**5. No Android Studio:** aguarde o Gradle terminar de sincronizar, escolha um emulador (ou conecte seu celular com **depuração USB** ativada) e clique no botão ▶ **Run**.

**Testar com o servidor local (opcional):** com o `npm run dev` rodando, use no `capacitor.config.ts`:

```ts
server: {
  url: "http://10.0.2.2:3000",
  cleartext: true,
},
```

(`10.0.2.2` é como o emulador Android enxerga o `localhost` do seu computador.) Rode `npx cap sync android` depois de alterar.

> ⚠️ Documentação oficial: <https://capacitorjs.com/docs/android>
>
> ⚠️ Atenção: o login do Google dentro de WebView costuma ser bloqueado. Se usar login social no Clerk, teste cedo (e-mail e senha funciona normalmente).
>
> ⚠️ Para publicar na Play Store é preciso uma conta de desenvolvedor Google (<https://play.google.com/console>), assinatura do app e Política de Privacidade.

---

## 🌐 Publicar online (Vercel)

1. Envie o código para o seu GitHub.
2. Entre em <https://vercel.com/> com o GitHub e clique em **Add New → Project**.
3. Escolha o repositório e, em **Environment Variables**, cadastre as mesmas variáveis do `.env.local` (trocando `NEXT_PUBLIC_APP_URL` pelo endereço da Vercel).
4. Clique em **Deploy**.
5. No painel do Stripe, crie um webhook apontando para `https://seu-app.vercel.app/api/webhooks/stripe` e use o segredo gerado em `STRIPE_WEBHOOK_SECRET`.

---

## 🩺 Problemas comuns

| Problema | Solução |
|---|---|
| `node` ou `npm` "não é reconhecido" | Feche e abra o terminal; se continuar, reinstale o Node.js |
| Erro de conexão com o banco | Confira o `DATABASE_URL` (precisa terminar com `?sslmode=require`) |
| Tela de login do Clerk não abre | Confira as duas chaves do Clerk no `.env.local` e reinicie o `npm run dev` |
| Página mostra vazio / sem cursos | Rode `npm run db:seed` |
| Porta 3000 ocupada | Rode `npm run dev -- -p 3001` e ajuste `NEXT_PUBLIC_APP_URL` |
| Mudei o `.env.local` e nada mudou | Pare (`Ctrl + C`) e rode `npm run dev` de novo |

---

## 🗺 Roadmap

- [x] Publicar o código-fonte
- [ ] Criar identidade visual própria (nome, logo e mascote)
- [ ] Criar conteúdo próprio de lições
- [ ] Traduzir a interface para português
- [ ] Política de Privacidade e Termos de Uso (LGPD)
- [ ] Transformar em PWA
- [ ] Publicar versão Android

---

## 📜 Créditos, licenças e direitos autorais

Este projeto é **uma obra em desenvolvimento** e, no momento, **não possui licença de uso, cópia ou redistribuição** (todos os direitos reservados ao autor das partes originais).

Tecnologias e referências:

- Como referência de arquitetura e estudo, foi consultado o repositório público [Davronov-Alimardon/duolingo-clone](https://github.com/Davronov-Alimardon/duolingo-clone). Esse repositório não declara licença, por isso nenhum código ou arquivo dele deve ser considerado licenciado para reutilização sem autorização do autor.
- Bibliotecas de terceiros (Next.js, React, Tailwind CSS, Drizzle ORM, shadcn/ui etc.) seguem suas respectivas licenças.
- Imagens, sons e vozes utilizados no projeto devem ser de autoria própria ou ter licença que permita o uso, com os devidos créditos.

---

<p align="center">
  Feito por <a href="https://github.com/eduardogrigorio"><b>Eduardo Grigório</b></a>
</p>
