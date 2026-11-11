# CLAUDE.md — AI Assistant Conventions

This file tells Claude Code (and other AI assistants) about this project's stack,
conventions, and rules. It is the single source of truth for AI-assisted development.

---

## Project Overview

**Name**: AI-Powered Web App (Capstone)  
**Track**: AI Developer Track  
**Purpose**: Full-stack capstone demonstrating AI-assisted development

---

## Tech Stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| Frontend | React 18 (Vite) | SPA, JSX, component-based |
| Backend | Node.js 20 + Express 4 | REST API |
| Database | PostgreSQL 16 | via `pg` / Prisma ORM |
| Styling | Vanilla CSS / CSS Modules | No Tailwind unless asked |
| Testing | Jest (backend) + Vitest (frontend) | |
| Linting | ESLint + Prettier | Config in root |
| AI Tooling | Claude Code (Anthropic) | |

---

## Directory Layout

```
capstone/
├── client/          # React frontend (Vite)
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   └── utils/
├── server/          # Express backend
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   └── middleware/
├── docs/            # Architecture decisions, API docs
├── .gitignore
├── CLAUDE.md        ← you are here
└── README.md
```

---

## Coding Conventions

### General
- Use **ES Modules** (`import`/`export`) throughout — no CommonJS `require()`.
- Prefer **async/await** over raw Promise chains.
- Write **JSDoc comments** for all exported functions.
- Keep functions small: aim for < 40 lines per function.
- Avoid magic numbers — use named constants.

### Naming
| Entity | Convention | Example |
|--------|-----------|---------|
| Variables / functions | camelCase | `getUserById` |
| React components | PascalCase | `UserCard` |
| CSS classes | kebab-case | `user-card` |
| Constants | UPPER_SNAKE_CASE | `MAX_RETRIES` |
| Files | kebab-case | `user-card.jsx` |

### React
- Functional components only — no class components.
- Keep components in `client/src/components/`.
- One component per file.
- Extract reusable logic into custom hooks in `client/src/hooks/`.

### Express
- Group routes by resource in `server/routes/`.
- Controllers handle business logic; routes handle HTTP only.
- Always validate request bodies with a schema (e.g., Zod or Joi).
- Return consistent JSON: `{ data, error, meta }`.

---

## Commit Convention

This project follows **[Conventional Commits 1.0.0](https://www.conventionalcommits.org/)**.

```
<type>(<optional scope>): <short description>

[optional body]

[optional footer]
```

### Allowed Types
| Type | Use When |
|------|---------|
| `feat` | Adding a new feature |
| `fix` | Fixing a bug |
| `docs` | Documentation only changes |
| `style` | Formatting, no logic change |
| `refactor` | Restructuring, no feature/fix |
| `test` | Adding or updating tests |
| `chore` | Build system, tooling, deps |
| `perf` | Performance improvement |

### Examples
```
feat(auth): add JWT token refresh endpoint
fix(ui): correct mobile layout overflow on UserCard
docs: update README with Getting Started section
chore: add ESLint and Prettier config
```

---

## AI Assistant Rules

When I ask you (Claude / AI) to help with this project, please follow these rules:

1. **Follow the conventions above** — do not introduce new patterns without asking.
2. **Explain non-obvious changes** — add a brief comment or explanation when doing something clever.
3. **Suggest tests** — whenever you add a function, suggest a test case.
4. **Use Conventional Commits** — when asked to draft a commit message, format it correctly.
5. **Be conservative with dependencies** — prefer the packages already in `package.json`.
6. **Prefer readability** over cleverness.
7. **Ask before refactoring** — do not rename files or restructure directories without asking.
8. **Critique constructively** — when asked to review code, provide actionable feedback.

---

## Environment Variables

Never commit `.env` files. Use `.env.example` to document required keys:

```bash
# .env.example
PORT=3000
DATABASE_URL=postgresql://user:pass@localhost:5432/capstone
JWT_SECRET=change-me
NODE_ENV=development
```

---

## Branch Strategy

```
main          ← production-ready, protected
 └── develop  ← integration branch
      └── feature/<ticket>   ← feature branches
      └── fix/<ticket>       ← bug fix branches
      └── chore/<ticket>     ← tooling/config
```

PRs target `develop`; `develop` merges to `main` on release.
