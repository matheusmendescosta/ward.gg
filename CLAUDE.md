# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server with hot reload (tsx watch)
npm run build    # Compile TypeScript to dist/ via tsup
npm start        # Run compiled production server
```

No linting, formatting, or testing framework is configured yet.

## Architecture

Express.js + TypeScript API server. Entry point is [src/server.ts](src/server.ts), which imports the app from [src/app.ts](src/app.ts) and starts it on the port defined in [src/env/index.ts](src/env/index.ts).

### Environment Variables

Validated at startup with Zod in [src/env/index.ts](src/env/index.ts). Add new env vars there before using them elsewhere. Required vars: `PORT`.

### Path Aliases

`@/*` maps to `./src/*` (defined in tsconfig). Use this for imports within `src/`.

### Intended Structure (placeholders in place)

- [src/http/routes/](src/http/routes/) — Express route definitions
- [src/http/controllers/](src/http/controllers/) — Request handlers
- [src/http/middlewares/](src/http/middlewares/) — Express middleware
- [src/services/](src/services/) — Business logic
- [src/repositories/](src/repositories/) — Data access layer
- [src/lib/](src/lib/) — Third-party client setup
- [src/utils/](src/utils/) — Shared utilities
