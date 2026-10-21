# griglingo.com.br
# 🦉GRIGlINGO 

> Plataforma web de aprendizado de idiomas com lições gamificadas, inspirada no Duolingo. Construída com **Next.js 14**, **React**, **Tailwind CSS**, **Drizzle ORM** e **PostgreSQL**.

<!-- Troque os links abaixo pelos seus -->
[**🔗 Demo online**](https://seu-app.vercel.app) · [**🐛 Reportar bug**](https://github.com/SEU-USUARIO/SEU-REPOSITORIO/issues) · [**💡 Sugerir melhoria**](https://github.com/SEU-USUARIO/SEU-REPOSITORIO/issues)

![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4?logo=tailwindcss&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Neon-4169E1?logo=postgresql&logoColor=white)

---

## 📑 Índice

- [Sobre o projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias](#-tecnologias)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação](#-instalação)
- [Variáveis de ambiente](#-variáveis-de-ambiente)
- [Banco de dados](#-banco-de-dados)
- [Rodando o projeto](#-rodando-o-projeto)
- [Personalizando o conteúdo](#-personalizando-o-conteúdo)
- [Estrutura de pastas](#-estrutura-de-pastas)
- [Deploy gratuito](#-deploy-gratuito)
- [Versão Android](#-versão-android)
- [Roadmap](#-roadmap)
- [Contribuindo](#-contribuindo)
- [Créditos e licença](#-créditos-e-licença)

---

## 📖 Sobre o projeto

Este projeto é uma aplicação full-stack para aprendizado de idiomas em formato de **trilhas de lições**, com sistema de vidas, pontos de experiência (XP), ranking e missões. O objetivo é oferecer uma experiência de estudo curta, divertida e que incentive a prática diária.

O código é baseado no projeto open source [Davronov-Alimardon/duolingo-clone](https://github.com/Davronov-Alimardon/duolingo-clone), adaptado e personalizado por **SEU NOME**.

> ⚠️ **Aviso:** este é um projeto educacional e **não é afiliado ao Duolingo**. "Duolingo" é marca registrada de seus respectivos donos. Para uso público ou comercial, utilize nome, logo e personagens próprios.

---

## ✨ Funcionalidades

- 🌐 Next.js 14 com **Server Actions**
- 🗺️ Trilha de cursos, unidades e lições
- ❓ Desafios interativos (seleção e assistência por áudio)
- 🔊 Efeitos sonoros e vozes geradas por IA
- ❤️ Sistema de **vidas (hearts)**
- 🌟 Sistema de **pontos / XP**
- 💔 Pop-up de "sem vidas restantes"
- 🚪 Confirmação ao sair de uma lição
- 🔄 Praticar lições antigas para recuperar vidas
- 🏆 **Ranking (leaderboard)**
- 🎯 **Missões (quests)** por marcos de pontos
- 🛍️ **Loja**: troque pontos por vidas
- 💳 **Plano Pro** com vidas ilimitadas (Stripe)
- 🔐 Autenticação com **Clerk**
- 🏠 Landing page
- 📊 **Painel administrativo** (React Admin) para gerenciar cursos, lições e desafios
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
| Estado | [Zustand](https://zustand-demo.pmnd.rs/) (pasta `store/`) |
| Deploy | [Vercel](https://vercel.com/) |

---

## ✅ Pré-requisitos

- **Node.js 18.17 ou superior** (recomendado: 20 LTS)
- **npm** (já vem com o Node)
- **Git**
- Contas gratuitas em:
  - [Clerk](https://clerk.com/) — autenticação
  - [Neon](https://neon.tech/) — banco PostgreSQL
  - [Stripe](https://stripe.com/) — *opcional*, apenas para o plano Pro

---

## 🚀 Instalação

```bash
# 1. Clone o repositório
git clone https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git

# 2. Entre na pasta
cd SEU-REPOSITORIO

# 3. Instale as dependências
npm install
```

> 💡 Se houver conflito de dependências, tente `npm install --legacy-peer-deps`.

---

## 🔑 Variáveis de ambiente

Crie um arquivo `.env.local` na raiz do projeto:

```env
# Clerk (https://dashboard.clerk.com)
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=""
CLERK_SECRET_KEY=""

# Neon / PostgreSQL (https://console.neon.tech)
DATABASE_URL="postgresql://usuario:senha@host/banco?sslmode=require"

# Stripe (opcional — necessário apenas para o plano Pro)
STRIPE_API_KEY=""
STRIPE_WEBHOOK_SECRET=""

# URL base da aplicação
NEXT_PUBLIC_APP_URL="http://localhost:3000"
```

| Variável | Onde obter |
|---|---|
| `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` / `CLERK_SECRET_KEY` | Painel do Clerk → *API Keys* |
| `DATABASE_URL` | Painel do Neon → *Connection string* |
| `STRIPE_API_KEY` | Painel do Stripe → *Developers → API keys* |
| `STRIPE_WEBHOOK_SECRET` | Painel do Stripe → *Developers → Webhooks* |
| `NEXT_PUBLIC_APP_URL` | `http://localhost:3000` em desenvolvimento; a URL final em produção |

> 🔒 **Nunca** envie o `.env.local` para o GitHub. Ele já está no `.gitignore`.

---

## 🗄 Banco de dados

Crie as tabelas com o Drizzle:

```bash
npm run db:push
```

Popule o banco com os cursos e lições iniciais:

```bash
npm run db:seed
```

> ⚠️ O script de seed normalmente **apaga e recria** os dados. Não o execute em produção se já houver usuários e progresso salvos.

Existe também o script `npm run db:prod`, que executa o seed em modo de produção (confira o conteúdo em `scripts/`).

---

## ▶️ Rodando o projeto

```bash
npm run dev
```

Acesse [http://localhost:3000](http://localhost:3000).

**Testar no celular (mesma rede Wi-Fi):**

```bash
npm run dev -- -H 0.0.0.0
```

Depois abra `http://IP-DO-SEU-COMPUTADOR:3000` no navegador do celular.

---

## 🎨 Personalizando o conteúdo

### Cursos, unidades, lições e desafios
- Edite o script de seed na pasta `scripts/` e rode `npm run db:seed` novamente; **ou**
- Use o **painel administrativo** (React Admin) para cadastrar tudo pela interface, sem mexer no código.

### Visual e marca
- Logos, mascote, bandeiras e áudios: pasta `public/`
- Cores e tema: `tailwind.config.ts`
- Componentes de interface: pasta `components/`

### Regras do jogo
- Quantidade de vidas, custo dos pontos na loja e outros valores: `constants.ts`

### Idioma da interface
- Os textos estão em inglês por padrão. Traduza-os nos componentes em `components/` e nas páginas em `app/`.

### Áudio
- Gere seus áudios (ElevenLabs, Google TTS etc.), salve em `public/` e referencie os arquivos no seed. Evite gerar áudio em tempo real para não consumir cota de APIs.

---

## 📂 Estrutura de pastas

```
.
├── actions/          # Server Actions (progresso, vidas, pontos, assinatura)
├── app/              # Rotas e páginas (App Router do Next.js)
├── components/       # Componentes reutilizáveis (UI e shadcn/ui)
├── db/               # Schema e conexão do banco (Drizzle)
├── lib/              # Funções utilitárias e helpers
├── public/           # Imagens, ícones, sons e áudios
├── scripts/          # Scripts de seed e reset do banco
├── store/            # Estado global (modais, etc.)
├── constants.ts      # Constantes do app (vidas, pontos, etc.)
├── drizzle.config.ts # Configuração do Drizzle ORM
├── middleware.ts     # Proteção de rotas (Clerk)
├── next.config.mjs   # Configuração do Next.js
└── tailwind.config.ts
```

---

## ☁️ Deploy gratuito

É possível rodar toda a infraestrutura em planos gratuitos:

| Serviço | Função |
|---|---|
| **GitHub** | Código-fonte |
| **Vercel (Hobby)** | Hospedagem do site e das Server Actions |
| **Neon (Free)** | Banco PostgreSQL |
| **Clerk (Hobby)** | Autenticação |

**Passo a passo (Vercel):**

1. Envie o projeto para o seu GitHub.
2. Em [vercel.com](https://vercel.com), clique em **Add New → Project** e importe o repositório.
3. Em **Environment Variables**, cadastre as mesmas variáveis do `.env.local`, trocando `NEXT_PUBLIC_APP_URL` pela URL final (`https://seu-app.vercel.app`).
4. Clique em **Deploy**.
5. No Clerk, adicione a URL de produção nos domínios permitidos.
6. *(Opcional)* No Stripe, crie um webhook apontando para `https://seu-app.vercel.app/api/webhooks/stripe` e copie o segredo para `STRIPE_WEBHOOK_SECRET`.

> ⚠️ **Atenção:** o plano Hobby da Vercel é restrito a **uso pessoal e não comercial**. Se você for cobrar assinaturas, exibir anúncios ou aceitar doações, será necessário um plano pago ou outra hospedagem.
>
> Os limites dos planos gratuitos mudam com frequência. Confira sempre as páginas oficiais de preços.

---

## 📱 Versão Android

O projeto é web e responsivo, então já funciona no Chrome do Android. Para ter um app instalável:

| Abordagem | Esforço | Observações |
|---|---|---|
| **PWA** (manifest + service worker) | Baixo | Instalável pela opção "Adicionar à tela inicial" |
| **TWA** (Bubblewrap / PWABuilder) | Baixo | Publica o PWA na Play Store |
| **Capacitor** + Android Studio | Médio | Acesso a recursos nativos (ex.: notificações push) |
| **Kotlin + Jetpack Compose** | Alto | App 100% nativo; exige criar API routes (JSON) para substituir as Server Actions |

> 💳 Para vender itens digitais dentro de apps na Play Store, o Google normalmente exige o **Google Play Billing**. Verifique as políticas atuais antes de usar Stripe no app.

---

## 🗺 Roadmap

- [ ] Traduzir toda a interface para português
- [ ] Adicionar novos idiomas e cursos
- [ ] Transformar em PWA
- [ ] Notificações de lembrete de estudo
- [ ] Modo offline para lições já baixadas
- [ ] Publicar versão Android
- [ ] Testes automatizados

---

## 🤝 Contribuindo

Contribuições são bem-vindas!

1. Faça um **fork** do projeto
2. Crie uma branch: `git checkout -b feature/minha-feature`
3. Faça o commit: `git commit -m "feat: minha nova feature"`
4. Envie: `git push origin feature/minha-feature`
5. Abra um **Pull Request**

---

## 📜 Créditos e licença

- Projeto base: [Davronov-Alimardon/duolingo-clone](https://github.com/Davronov-Alimardon/duolingo-clone), baseado em um tutorial de 2024 sobre Next.js, React e Drizzle.
- Personagens: pacote de [Kenney](https://kenney.nl/) — confira a licença de uso.
- Vozes: [ElevenLabs](https://elevenlabs.io/) — confira os termos do seu plano.

> O repositório original não exibe um arquivo de licença. Antes de usar este projeto comercialmente, verifique as permissões com o autor original e adicione um arquivo `LICENSE` adequado ao seu caso.

---

<p align="center">
  Feito com ❤️ por <a href="https://github.com/SEU-USUARIO"><b>SEU NOME</b></a>
</p>
