# Turborepo Template

A monorepo template built with Turborepo, pnpm and Next.js, designed for modern web application development with Docker deployment support.

## Project Structure

```
turborepo-template/
├── apps/                     # Application code
│   └── recruiter-dashboard/  # Next.js recruiting dashboard application
├── packages/                 # Shared libraries and configurations
│   ├── eslint-config/        # Shared ESLint configurations
│   └── typescript-config/    # Shared TypeScript configurations
├── docker-compose.yml        # Docker Compose configuration
├── turbo.json                # Turborepo configuration
└── pnpm-workspace.yaml       # pnpm workspace configuration
```

## Technology Stack

- **Package Manager**: pnpm v9.15.1
- **Build System**: Turborepo
- **Framework**: Next.js 15
- **Languages**: TypeScript, React 19
- **Containerization**: Docker
- **Development Utilities**: ESLint, TypeScript configuration

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v22 recommended)
- [pnpm](https://pnpm.io/) v9.15.1
- [Docker](https://www.docker.com/) and Docker Compose

### Development Setup

1. Install dependencies:

```bash
pnpm install
```

2. Start the development server:

```bash
pnpm dev
```

### Building for Production

```bash
pnpm build
```

### Docker Deployment

#### Build production images using BuildKit

```bash
COMPOSE_DOCKER_CLI_BUILD=1 DOCKER_BUILDKIT=1 docker-compose -f docker-compose.yml build
```

#### Start production in detached mode

```bash
docker-compose -f docker-compose.yml up -d
```

#### Stop running containers

```bash
docker-compose -f docker-compose.yml down
```

## Available Scripts

- `pnpm dev` - Start the development server
- `pnpm build` - Build all packages and applications
- `pnpm lint` - Run linting across all packages
- `pnpm clean` - Clean build outputs
- `pnpm format` - Format code with Prettier

## Docker Network

The application uses an external Docker network named `app_network`. Make sure to create this network before deploying:

```bash
docker network create app_network
```
