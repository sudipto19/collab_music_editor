# Collab Music Editor

yeah it's a real-time collaborative drawing thing. supposed to be for music scores but honestly it's just canvas stuff for now.

## What's in here

- **excelidraw-frontend** - Next.js app with canvas drawing. has auth pages and room-based collaboration
- **http-backend** - Express server handling REST endpoints (signup/signin, room creation, fetching chats)
- **ws-backend** - WebSocket server for real-time sync between users in rooms
- **web** - another Next.js frontend (chat room ui, might merge this later idk)

**shared packages:**
- `@repo/db` - Prisma client + schema (postgres). users, rooms, chats
- `@repo/common` - zod schemas for validation
- `@repo/backend-common` - shared backend utils
- `@repo/ui` - react components
- `@repo/eslint-config` + `@repo/typescript-config` - you know what these are

## Stack

TypeScript, Next.js 15, Express, WebSocket (ws), Prisma, PostgreSQL, Turborepo

## Running this

```bash
pnpm install
pnpm dev
```

set up your `.env` with `DATABASE_URL` and `JWT_SECRET` or whatever. run migrations with `prisma migrate dev` in the db package.

## Features

- JWT auth (signup/signin)
- room-based collaboration (create/join rooms)
- real-time canvas drawing with WebSocket sync
- persistent storage in postgres
- monorepo with turborepo so you can run everything at once

---

*work in progress. actual music notation rendering to be added soon*
