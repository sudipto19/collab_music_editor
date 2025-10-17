# Real-Time Collaborative Music Score Editor

A collaborative drawing platform built with real-time synchronization capabilities, designed as a foundation for music score editing and collaborative diagram creation.

## Tech Stack

**Frontend:** TypeScript, Next.js 15, React 19, Canvas API, Tailwind CSS  
**Backend:** Express, WebSocket (ws), Node.js  
**Database:** PostgreSQL, Prisma ORM  
**Infrastructure:** Turborepo monorepo, pnpm workspaces

## Key Features

• **Real-time Collaborative Drawing Platform** - Built WebSocket synchronization supporting multiple concurrent users editing the same canvas simultaneously

• **Canvas API Rendering Engine** - Engineered shape manipulation system with live preview, drawing tools (pencil, shapes), and persistent storage of all drawing operations

• **Monorepo Architecture** - Designed scalable architecture using Turborepo managing multiple frontend/backend services and shared packages with optimized build pipeline

• **JWT Authentication System** - Implemented secure authentication flow with PostgreSQL database and room-based access control for collaborative sessions

• **Room-based Collaboration** - Users can create and join drawing rooms with unique identifiers, enabling isolated collaborative workspaces

## Project Structure

### Applications

- **excelidraw-frontend** - Next.js application featuring canvas drawing interface, authentication pages, and room-based collaboration UI
- **http-backend** - Express REST API server handling user registration, authentication, room management, and chat message persistence
- **ws-backend** - WebSocket server managing real-time drawing synchronization and message broadcasting across connected clients
- **web** - Additional Next.js frontend for chat room interface and real-time messaging

### Shared Packages

- **@repo/db** - Prisma client configuration and database schema (Users, Rooms, Chats models)
- **@repo/common** - Shared TypeScript types and Zod validation schemas
- **@repo/backend-common** - Common backend utilities and middleware
- **@repo/ui** - Reusable React component library
- **@repo/eslint-config** - Shared ESLint configuration
- **@repo/typescript-config** - Shared TypeScript compiler configurations

## Getting Started

### Prerequisites
- Node.js 18 or higher
- PostgreSQL database
- pnpm package manager

### Installation

```bash
# Install dependencies
pnpm install

# Set up environment variables
# Create .env files with:
# - DATABASE_URL (PostgreSQL connection string)
# - JWT_SECRET (for authentication)

# Run database migrations
cd packages/db
pnpm prisma migrate dev

# Start development servers
pnpm dev
```

## Architecture Highlights

- **Turborepo** orchestrates the monorepo build system with intelligent caching and parallel task execution
- **WebSocket protocol** enables sub-100ms latency for real-time drawing synchronization
- **Prisma ORM** provides type-safe database queries with automatic migration management
- **Shared workspace packages** eliminate code duplication across frontend and backend services

---

*Project Status: Ongoing development - Music notation rendering features planned for future iterations*