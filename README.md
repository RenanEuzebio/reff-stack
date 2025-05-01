# Reff Stack

This is my personal webdev stack.

## 🖥️ Main Server

Hosted on its own [(Hetzner VPS)](https://www.hetzner.com/cloud).

### 🧠 Central Control & Dev Hub

- **🧭 Container Management:** [Portainer CE](https://www.portainer.io/)  
  Centrally manages all site VPSs via Portainer Agents.

- **🗃️ Version Control:** [Gitea](https://gitea.io/)  
  Hosts all site repositories for development and staging.

- **📉 Analytics:** [Umami](https://umami.is/)  
  Tracks multiple domains with privacy-first analytics.

---

## 🏗️ Site Backend

Each site backend is hosted on its own [(Hetzner VPS)](https://www.hetzner.com/cloud) instance and contains an isolated production stack. DB backups are sent to [Cloudflare R2](https://www.cloudflare.com/products/r2/).

- **Docker Container 1: Python API**
  - Framework: [Litestar](https://litestar.dev/)
  - Dependency & environment management: [UV](https://github.com/astral-sh/uv)

- **Docker Container 2: Pocketbase**
  - Lightweight backend for DB and Auth: [Pocketbase](https://pocketbase.io/)

- **Portainer Agent:**  
  - Enables remote container management from the main server.

---

## 🌐 Site Frontend

Each static site frontend is hosted on its own [(Cloudflare Pages)](https://pages.cloudflare.com/) instance after passing development checks on the main server.

- **Client Interactivity:** [Alpine.js](https://alpinejs.dev/)
- **Server Interactivity (AJAX without JS):** [HTMX](https://htmx.org/)
- **Styling:** [Pico CSS](https://picocss.com/)
- **Icons:** [Lucide Icons](https://lucide.dev/)

## 🔐 Optional: Internal Networking

Use [Tailscale](https://tailscale.com/) or [WireGuard](https://www.wireguard.com/) for secure communication between servers and Portainer agents without exposing Docker ports to the public internet.

---

## 🔁 Development Workflow

1. Developers push code to **Gitea** on the main server.
2. Development builds and staging environments are optionally spun up via **Portainer** for testing.
3. When ready:
   - **Static frontend** is deployed to **Cloudflare Pages**.
   - **Production containers** are redeployed on the appropriate **Site VPS** using Portainer.


## To do

- Payment (Probably Stripe)  
- Localization Manager  
- Determine if the whole setup GDPR compliant without using cookies?
