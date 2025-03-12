# AgentifyMe Worker Manager Service

## Overview

This Docker service configuration sets up the AgentifyMe Worker Manager, a containerized service designed to manage workers dynamically.

## Service Configuration

### Docker Image

- **Image:** `ghcr.io/agentifyme/worker-manager:0.1`
- **Container Name:** `agnt5-worker-manager`

### Runtime Behavior

- **Pull Policy:** Always fetch the latest image
- **Restart Policy:** Restart unless explicitly stopped
- **Entrypoint Command:** `/app/main`

### Environment Configuration

- Uses `.env` file for environment variables
- Sets `SERVICE_NAME` to `agentifyme-worker-manager`

### Volumes

- Mounts Docker socket for container management
- Binds local `config.toml` to `/etc/agentifyme/nodemanager.toml`

## Prerequisites

- Docker
- Docker Compose
- Local `.env` file
- Local `config.toml` configuration file

## Deployment

```bash
docker-compose up -d worker-manager
```

## Notes

- Requires access to Docker socket
- Configuration can be customized via `.env` and `config.toml`

## ENVs

```sh
AGENTIFYME_API_KEY=""
AGENTIFYME_ORGANIZATION_ID=""
```
