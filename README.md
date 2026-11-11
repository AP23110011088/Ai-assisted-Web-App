# AI-Powered Web App — Capstone Project

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/Node.js-20_LTS-green.svg)
![Commits](https://img.shields.io/badge/Commits-Conventional-orange.svg)
![AI Tooling](https://img.shields.io/badge/AI-Claude_Code-purple.svg)

> A full-stack web application built with AI-assisted development as part of the AI Developer Track capstone.

## Overview

This project demonstrates end-to-end AI-assisted software development using modern tooling (Claude Code / Cursor), conventional commits, and a Node.js + Express + React stack.

## Why This Project?

AI-assisted development is rapidly changing how software gets built. This capstone explores that shift hands-on:

- **Pair with AI** at every step — planning, coding, reviewing, and committing
- **Learn Conventional Commits** as a professional standard enforced from day one
- **Build a reproducible workflow** that any team member (or AI) can follow via `CLAUDE.md`
- **Ship real features** while measuring how AI tooling affects velocity and code quality

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

## Contributing

1. Fork the repo and create a branch: `git checkout -b feature/my-feature`
2. Follow the conventions in [CLAUDE.md](./CLAUDE.md)
3. Commit using Conventional Commits format
4. Open a Pull Request targeting `develop`

## License

MIT — see [LICENSE](./LICENSE) for details.
