# AI-Powered Web App — Capstone Project

> A full-stack web application built with AI-assisted development as part of the AI Developer Track capstone.

## Overview

This project demonstrates end-to-end AI-assisted software development using modern tooling (Claude Code / Cursor), conventional commits, and a Node.js + Express + React stack.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React (Vite) |
| Backend | Node.js + Express |
| Database | PostgreSQL |
| AI Tooling | Claude Code (Anthropic) |
| Version Control | Git + GitHub |

## Project Structure

```
capstone/
├── client/          # React frontend
├── server/          # Express backend
├── docs/            # Project documentation
├── .gitignore
├── CLAUDE.md        # AI assistant conventions
└── README.md
```

## Getting Started

### Prerequisites

- Node.js >= 20 (LTS)
- Git >= 2.x
- npm >= 10

### Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/capstone.git
cd capstone

# Install dependencies
npm install

# Start development servers
npm run dev
```

## Conventions

- **Commits**: [Conventional Commits 1.0.0](https://www.conventionalcommits.org/)
- **Branches**: `feature/<name>`, `fix/<name>`, `chore/<name>`
- **Code Style**: ESLint + Prettier (config in repo root)

## License

MIT — see [LICENSE](./LICENSE) for details.
