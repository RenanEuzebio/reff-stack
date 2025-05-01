# Reff Stack

## 🖥️ Server [(Hetzner VPS)](https://www.hetzner.com/cloud)

Docker containers orchestrated using [Komodo](https://komo.do/).

### 🐍 Docker Container 1: Python API
- Framework: [Litestar](https://litestar.dev/)
- Dependency & environment management: [UV](https://github.com/astral-sh/uv)

### 📦 Docker Container 2: Pocketbase
- Lightweight backend for DB and Auth: [Pocketbase](https://pocketbase.io/)

---

## 🌐 Client [(Cloudflare Pages)](https://pages.cloudflare.com/)

- **Client Interactivity:** [Alpine.js](https://alpinejs.dev/)
- **Server Interactivity (AJAX without JS):** [HTMX](https://htmx.org/)
- **Styling:** [Pico CSS](https://picocss.com/)
- **Icons:** [Lucide Icons](https://lucide.dev/)

---

## 🧾 Versioning and Backups

- **Version Control:** [Gitea](https://gitea.io/)
- **Static assets & DB backups storage:** [Cloudflare R2](https://www.cloudflare.com/products/r2/)

*Pocketbase DB backups are regularly synced to R2.*

## To add

- Analytics;
- Payment (Probabily Stripe);
- Localization Manager.
- How do I implement cookies?
