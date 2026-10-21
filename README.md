# 🦉 Tytos - aprendizado para idiomas

> Plataforma web de aprendizado de idiomas com lições curtas e gamificadas (vidas, XP, ranking e missões).

**Status:** 🚧 em desenvolvimento. O código-fonte ainda não foi publicado neste repositório.

![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4?logo=tailwindcss&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Neon-4169E1?logo=postgresql&logoColor=white)

---

## 📖 Sobre o projeto

O Griglingo é um projeto de estudo de desenvolvimento full-stack. A ideia é oferecer uma experiência de aprendizado de idiomas em **trilhas de lições**, com sistema de vidas, pontos de experiência (XP), ranking e missões.

> ⚠️ **Aviso:** este é um projeto independente e educacional. **Não possui qualquer relação, afiliação ou endosso de terceiros** que ofereçam serviços semelhantes. Todas as marcas citadas pertencem aos seus respectivos titulares.

---

## ✨ Funcionalidades planejadas

- 🗺️ Trilha de cursos, unidades e lições
- ❓ Desafios interativos
- ❤️ Sistema de vidas
- 🌟 Pontos de experiência (XP)
- 🏆 Ranking
- 🎯 Missões por marcos de pontos
- 🛍️ Loja para trocar pontos por vidas
- 🔐 Autenticação de usuários
- 📊 Painel administrativo de conteúdo
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
| Hospedagem | [Vercel](https://vercel.com/) |

---

## ✅ Pré-requisitos

- Node.js 18.17 ou superior (recomendado: 20 LTS)
- npm e Git
- Contas gratuitas no Clerk e no Neon

---

## 🚀 Como rodar localmente

> As instruções abaixo valem a partir da publicação do código.

```bash
git clone https://github.com/eduardogrigorio/griglingo.com.br.git
cd griglingo.com.br
npm install
```

Crie o arquivo `.env.local` na raiz (**nunca** envie este arquivo ao GitHub):

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=""
CLERK_SECRET_KEY=""
DATABASE_URL="postgresql://usuario:senha@host/banco?sslmode=require"
NEXT_PUBLIC_APP_URL="http://localhost:3000"
```

Crie as tabelas, popule o banco e inicie:

```bash
npm run db:push
npm run db:seed
npm run dev
```

Acesse <http://localhost:3000>.

---

## 🗺 Roadmap

- [ ] Publicar o código-fonte
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
