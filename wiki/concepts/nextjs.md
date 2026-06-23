---
concept: nextjs
entity_type: concept
aliases: ["Next.js", "Next"]
sources: ["raw\\backend_roadmap.md", "raw\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-23T04:14:36Z
---

## Definition

Next.js is a **React-based full-stack framework** that enables both frontend and backend development within a single project. Built on top of [[react]] and running on [[nodejs]], it provides a complete solution for building modern web applications with server-side rendering (SSR), static site generation (SSG), incremental static regeneration (ISR), and API routes.

Created and maintained by Vercel, Next.js has become one of the most popular React frameworks, offering conventions and optimizations that make it easier to build production-ready applications without manually configuring bundlers, routing, or code splitting.

## How it works

Next.js extends React by adding a **file-system based router**, where pages and API routes are defined by files in the `pages/` or `app/` directory (depending on the router version). The framework handles the complex orchestration between client and server:

- **File-based Routing** — Files in `pages/` or `app/` automatically become routes (e.g., `pages/about.tsx` → `/about`)
- **Hybrid Rendering** — Each page can choose its rendering strategy: SSR, SSG, ISR, or client-side rendering (CSR)
- **API Routes** — Files in `pages/api/` or `app/api/` become serverless API endpoints (e.g., `pages/api/users.ts` → `/api/users`)
- **Automatic Code Splitting** — Only the JavaScript needed for the current page is loaded
- **Server Components** (App Router) — Components that run exclusively on the server, reducing client-side JavaScript

## Rendering Strategies

Next.js supports multiple rendering approaches, which can be mixed within the same application:

| Strategy | Description | Best For |
|----------|-------------|----------|
| **SSR** (Server-Side Rendering) | Page is rendered on each request at server | Dynamic content, personalized pages |
| **SSG** (Static Site Generation) | Page is pre-built at compile time as static HTML | Blogs, marketing pages, docs |
| **ISR** (Incremental Static Regeneration) | SSG with periodic revalidation; static + fresh | E-commerce, content sites with frequent updates |
| **CSR** (Client-Side Rendering) | Page shell is static, data fetched client-side | Dashboards, authenticated pages |
| **RSC** (React Server Components) | Components run on server, stream HTML to client | Data-heavy UIs, reducing bundle size |

## Key Features

- **App Router** (Next.js 13+) — New routing paradigm built on React Server Components with nested layouts, loading states, and error boundaries
- **Server Actions** — Directly call server-side functions from client components via `"use server"`
- **Middleware** — Run code before a request completes (auth redirects, A/B testing, rewrites)
- **Built-in Optimizations** — Image optimization (`next/image`), font optimization, script loading, SEO support
- **Edge Runtime** — Deploy API routes and middleware to Vercel Edge Functions globally
- **Static Exports** — Export as fully static site for hosting on any CDN

## Ecosystem & Comparison

Next.js is part of a family of full-stack meta-frameworks built on top of UI libraries:

- **[[react]] + Next.js** — React is the UI library; Next.js is the full-stack framework around it
- **[[vue]] + Nuxt.js** — Vue's equivalent of Next.js (also known as Nuxt)
- **Remix** — Alternative React full-stack framework focused on web fundamentals and progressive enhancement
- **Gatsby** — React-based static site generator (SSG-focused, less flexible for dynamic content)

## Use Cases

- **Marketing Sites** — SSG for blazing fast static pages
- **E-commerce** — ISR for product pages that update without full rebuild
- **SaaS Applications** — SSR + API routes for authenticated, dynamic experiences
- **Blogs & Documentation** — SSG with MDX content, great SEO
- **Full-Stack Applications** — One codebase for frontend UI and backend API endpoints, simplifying deployment

## Trade-offs

### Strengths
- **Developer Experience** — Zero-config setup, file-based routing, hot reload, TypeScript support out of the box
- **SEO Friendly** — SSR/SSG produce fully rendered HTML for search engines, unlike pure SPAs
- **Performance** — Automatic image optimization, code splitting, and edge delivery
- **Full-Stack in One Project** — Frontend and backend in the same repo, simplifying full-stack integration (see raw/fullstack_integration.md)
- **Vast Ecosystem** — Leverages the entire React + npm ecosystem

### Limitations
- **Opinionated** — Frameworks like Express offer more flexibility; Next.js enforces its own routing and data-fetching patterns
- **Build Complexity** — SSG builds can be slow for large sites; ISR adds operational complexity
- **Vendor Lock-in** — Advanced features (ISR, Edge Functions) work best on Vercel; self-hosting requires more effort
- **Not a Full Backend Replacement** — For complex business logic, database-heavy operations, or long-running processes, a dedicated backend service ([[express]], NestJS) is still needed
- **Learning Curve** — Understanding when to use SSR vs SSG vs ISR vs RSC requires knowledge of the trade-offs

## Best Practices

1. **Choose the right rendering strategy per page** — Not every page needs SSR; use SSG where content is static
2. **Use `next/image`** — Automatic image optimization improves performance significantly
3. **Leverage Incremental Static Regeneration** — For content that changes, ISR offers the best of SSG and SSR
4. **Implement [[jwt]] authentication** — Use API routes with JWT tokens for secure API access
5. **Configure [[cors]] properly** — In API routes, set up CORS headers for cross-origin requests
6. **Adopt the App Router** — For new projects, the App Router provides better performance and Server Components
7. **Use environment variables** — Follow [[local-development-environment]] best practices for configuration
