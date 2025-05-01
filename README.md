# Reff Full-Stack

This is my personal WebDev stack.

---

## 🖥️ Main Server

Hosted on its own [(Hetzner VPS)](https://www.hetzner.com/cloud) instance and contains an isolated development stack.

### 🧠 Central Control & Dev Hub

- **🧭 Container Management:** [Komodo](https://github.com/mbecker20/komodo)  
  - The **Komodo Core** is installed here and manages all remote VPSs via **Komodo Periphery agents**.

- **🗃️ Version Control:** [Gitea](https://gitea.io/)  
  Hosts all site repositories for development and staging. Used to manage both frontend and backend source code.

- **📉 Analytics:** [Umami](https://umami.is/)  
  Tracks multiple domains with privacy-first, cookie-free analytics.

---

## 🏗️ Site Backend

Each site backend is hosted on its own [(Hetzner VPS)](https://www.hetzner.com/cloud) instance and contains an isolated production stack. DB backups are sent to [Cloudflare R2](https://www.cloudflare.com/products/r2/).

- **Docker Container 1: Python API**
  - Framework: [Litestar](https://litestar.dev/)
  - Dependency & environment management: [UV](https://github.com/astral-sh/uv)

- **Docker Container 2: Pocketbase**
  - Lightweight backend for DB and Auth: [Pocketbase](https://pocketbase.io/)

- **Komodo Periphery Agent:**  
  - Installed on each site VPS.
  - Connects to the central Komodo Core to allow remote orchestration.

---

## 🌐 Site Frontend

Each site frontend is hosted on its own [(Cloudflare Pages)](https://pages.cloudflare.com/) instance after passing development checks on the main server.

- **Client Interactivity:** [Alpine.js](https://alpinejs.dev/)
- **Server Interactivity (AJAX without JS):** [HTMX](https://htmx.org/)
- **Styling:** [Pico CSS](https://picocss.com/) + [Lucide Icons](https://lucide.dev/)

---

## 🔁 Development Workflow

1. Developers push code to **Gitea** on the main server.
2. Development builds and staging environments can be spun up via **Komodo**.
3. When ready:
   - The **static frontend** is deployed to **Cloudflare Pages**.
   - The **production containers** are redeployed on the appropriate **Site VPS** via Komodo.

---

## To do

- Payment (Probably Stripe)  
- Localization Manager  
