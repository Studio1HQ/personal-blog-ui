<div align="center">

<img src="https://raw.githubusercontent.com/Studio1HQ/Studio1HQ/main/assets/banners/personal-blog-ui.webp" alt="Personal Blog UI for Encore: A Next.js blog front end that reads posts from an Encore API" width="100%" />

<br />
<br />

# Personal Blog UI for Encore

### A Next.js blog front end that reads posts from an Encore API

A Next.js page that fetches blog posts from the personal-blog-encore backend with axios and renders them as a card grid with title, content, author and date.

<br />

[![Built by Studio1](https://img.shields.io/badge/Built_by_Studio1-f97316?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxNjAgMTYwIiBmaWxsPSJub25lIj48cGF0aCBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTAgMzVDMCAxNi42ODA3IDE0LjA3NDQgMS42NDg0NCAzMiAwLjEyNjk1M1YxNDFINTEuMDUyM0M1Mi40MzA4IDEzNy4zNDQgNTQuNzQ0NiAxMzMuNjg5IDU3Ljk5MzggMTMwLjAzM0M2MS4xNDQ2IDEyNi41MDggNjQuNjg5MiAxMjMuNDQgNjguNjI3NyAxMjAuODI5QzcyLjU2NjIgMTE4LjM0OSA3Ni4zNTY5IDExNi43ODIgODAgMTE2LjEyOVY4Ni43NTQ0Qzc1LjQ3MDggODcuOTI5MiA3MS4zODQ2IDg5LjY5MTkgNjcuNzQxNSA5Mi4wNDE1QzY0IDk0LjUyMjUgNjAuNzUwOCA5Ny40NiA1Ny45OTM4IDEwMC44NTRDNTYuNTM0NSAxMDIuNzIgNTUuMjU0NSAxMDQuNjU5IDU0LjE1MzkgMTA2LjY3MVYwSDEyNUMxNDQuMzMgMCAxNjAgMTUuNjY5OSAxNjAgMzVWMTI1QzE2MCAxNDQuMzMgMTQ0LjMzIDE2MCAxMjUgMTYwSDEyNFYxOEgxMDQuOTQ4QzEwMy41NjkgMjEuNjgxNiAxMDEuMjU1IDI1LjM2MjggOTguMDA2MiAyOS4wNDQ0Qzk0Ljg1NTQgMzIuNTk0MiA5MS4zMTA4IDM1LjY4NDEgODcuMzcyMyAzOC4zMTRDODMuNDMzOCA0MC44MTIgNzkuNjQzMSA0Mi4zODk2IDc2IDQzLjA0NzRWNzIuNjMwNEM4MC41MjkyIDcxLjQ0NzMgODQuNjE1NCA2OS42NzI0IDg4LjI1ODUgNjcuMzA1N0M5MiA2NC44MDc2IDk1LjI0OTIgNjEuODQ5MSA5OC4wMDYyIDU4LjQzMDdDOTkuNDY1NSA1Ni41NTEzIDEwMC43NDUgNTQuNTk4NiAxMDEuODQ2IDUyLjU3MjNWMTYwSDM1QzE1LjY3IDE2MCAwIDE0NC4zMyAwIDEyNVYzNVoiIGZpbGw9IiNmZmZmZmYiLz48L3N2Zz4K)](https://studio1hq.com)
[![Built with Encore](https://img.shields.io/badge/Built_with_Encore-141414?style=for-the-badge)](https://encore.dev)

[Encore docs](https://encore.dev/docs) &nbsp;·&nbsp; [Encore](https://encore.dev) &nbsp;·&nbsp; [More examples](https://github.com/Studio1HQ) &nbsp;·&nbsp; [studio1hq.com](https://studio1hq.com)

</div>

<br />

## Overview

A small Next.js front end for the [personal-blog-encore](https://github.com/Studio1HQ/personal-blog-encore) backend, an API built with [Encore](https://encore.dev). The single page fetches the list of posts from the API and shows them as a responsive card grid.

It is a minimal example of putting a Next.js client in front of an Encore service.

## Features

- **Post list**: calls `GET /blogs` and renders each post as a card with title, content, author and creation date.
- **Loading and error states**: shows a loading message while fetching and an error message if the request fails.
- **Responsive grid**: one column on mobile, two on medium screens, three on large screens.
- **Tailwind styling**: gradient background, rounded cards and hover shadows.

## Tech stack

| Layer | Tool |
| --- | --- |
| Framework | [Next.js](https://nextjs.org) 15 (App Router), React 19, TypeScript |
| Styling | [Tailwind CSS](https://tailwindcss.com) |
| HTTP client | [axios](https://axios-http.com) |
| Backend | [Encore](https://encore.dev), see [personal-blog-encore](https://github.com/Studio1HQ/personal-blog-encore) |

## Getting started

### Prerequisites

- Node.js 18 or later and npm
- A running [personal-blog-encore](https://github.com/Studio1HQ/personal-blog-encore) backend, or access to the staging URL already set in the code

### Installation

```bash
git clone https://github.com/Studio1HQ/personal-blog-ui.git
cd personal-blog-ui
npm install
```

### Environment variables

None. The API URL is hardcoded in `src/app/page.tsx`:

```ts
axios.get("https://staging-blogs-nqei.encr.app/blogs")
```

Replace it with your own Encore environment URL, or with `http://127.0.0.1:4000/blogs` when running the backend locally with `encore run`.

### Run

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000). Other scripts: `npm run build`, `npm run start`, `npm run lint`.

## How it works

`src/app/page.tsx` is a client component. On mount it requests `/blogs`, reads `response.data.blogs`, and stores the list in state. Each post has `id`, `title`, `content`, `author` and `created_at`. There is no routing, auth or write path in this front end.

## Resources

- [personal-blog-encore](https://github.com/Studio1HQ/personal-blog-encore): the Encore backend this UI reads from.
- [Encore docs](https://encore.dev/docs): framework documentation.
- [Encore](https://encore.dev): the backend platform.

<br />

---

<div align="center">

<a href="https://studio1hq.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Studio1HQ/website/main/brand/studio1-logo-on-dark.svg" />
    <img src="https://raw.githubusercontent.com/Studio1HQ/website/main/brand/studio1-logo-on-light.svg" alt="Studio1" width="160" />
  </picture>
</a>

Built by **[Studio1](https://studio1hq.com)**, the technical content and DevRel partner for devtool teams. Made with [Encore](https://encore.dev).<br />
Browse more open-source examples at [github.com/Studio1HQ](https://github.com/Studio1HQ).

[![Website](https://img.shields.io/badge/studio1hq.com-0b0807?style=for-the-badge&logo=googlechrome&logoColor=white)](https://studio1hq.com)
[![Book a call](https://img.shields.io/badge/Book_a_strategy_call-f97316?style=for-the-badge&logo=googlecalendar&logoColor=white)](https://cal.com/studio1/collab)
[![X](https://img.shields.io/badge/%40Studio1HQ-141414?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Studio1HQ)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/studio1hq/)

<sub><a href="https://studio1hq.com">studio1hq.com</a> · Technical content, docs, video and DevRel for devtools</sub>

</div>
