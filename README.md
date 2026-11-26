# Guini Crew Paperclip (Render)

Private deploy repo for hosting [Paperclip](https://github.com/paperclipai/paperclip) on Render for Guini Crew.

This repository contains only:

- `Dockerfile` — pulls the official public image `ghcr.io/paperclipai/paperclip:latest`

The live service runs in **authenticated** + **public** mode so the board can be opened in Safari (with login). After the first admin claims the instance, add the OpenRouter key under **Connectors → OpenRouter**.

## Render settings (do not put secrets in this repo)

- Workspace: Guini Productions LLC
- Region: Virginia
- Web service: `guini-paperclip` (Standard / 1 CPU, 2 GB RAM)
- Database: `guini-paperclip-db` (Basic 256 MB) — create a **new** database; do not reuse existing ones
- Health check: `GET /api/health`
- Recommended persistent disk: 2 GB mounted at `/paperclip` (`PAPERCLIP_HOME`)

Secrets and `DATABASE_URL` are stored as Render environment variables, not in git.
