# Reff Stack Overview

This stack is built with a focus on simplicity, performance, and modern tooling.

---

## Backend (Hetzner CX11 VPS)

### Container 1: PocketBase
- SQLite database
- User authentication
- Realtime API
- File uploads
- DB backup to Cloudflare R2

### Container 2: Litestar API
- Python backend logic
- Exposes endpoints for HTMX interactions

---

## Frontend (Cloudflare Pages)

- **HTMX** — dynamic HTML interactions via `GET`/`POST`
- **Pico CSS** — minimal, classless styling
- **Lucide Icons** — modern, lightweight SVG icons

---

## Storage

- **Cloudflare R2**
  - User-uploaded files (via PocketBase)
  - Periodic backups of the PocketBase database
