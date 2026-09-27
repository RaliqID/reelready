# ReelReady

Monorepo for short-form video tooling: a processing engine, a server, and a web front end. ReelReady wraps clip preparation and optimization into a reusable engine package that both the CLI and the app consume.

## Architecture

A workspace monorepo with three pieces:

| Package | Path | Responsibility |
|---|---|---|
| **engine** | `packages/engine` | Core clip analysis and optimization logic, exposed as a library and CLI |
| **server** | `apps/server` | HTTP API in front of the engine |
| **web** | `apps/web` | Browser front end for uploading and inspecting clips |

## Features

- Shared processing engine usable from CLI, server, or directly as a package
- Upload endpoint that accepts a clip and streams it through the engine
- Knowledge base for platform-specific constraints â€” e.g. Instagram Reels specs in `docs/kb/`
- Unit tests for both engine and server

## Tech Stack

- Node.js workspaces monorepo
- Engine + CLI in JavaScript
- Server: Express-style HTTP API
- Web: vanilla front end with a hand-rolled UI

## Project Structure

```
apps/
  server/     # API â€” src/app.js, src/index.js, test/
  web/        # front end â€” index.html, app.js, styles.css
packages/
  engine/     # src/cli.js, src/index.js, test/
docs/kb/      # platform knowledge base (e.g. instagram-reels.md)
```

## Getting Started

```bash
npm install
```

Run the server and web app from their respective `apps/` folders. Tests:

```bash
npm test
```

**Author:** Raliq Hidayat BM3
