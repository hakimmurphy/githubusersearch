# GitHub User Search (Vue 3 + Vite)

A lightweight Vue 3 single-page app that searches **GitHub users** using the REST API. Built with **Vite** for fast dev and a minimal build. Optional personal access token support helps avoid the default unauthenticated rate limit. :contentReference[oaicite:1]{index=1}

---

## ✨ Features
- Search for GitHub users by username and display profile data.
- Fast local dev with Vite; production build in seconds.
- Optional token auth to increase API rate limits. :contentReference[oaicite:2]{index=2}

---

## 🧰 Tech Stack
- **Vue 3**, **Vite**
- Vanilla CSS / HTML
- Folder layout with `src/` and `public/`. :contentReference[oaicite:3]{index=3}

---

## 🚀 Getting Started

### 1) Clone & install
```bash
git clone https://github.com/hakimmurphy/githubusersearch.git
cd githubusersearch
npm install
```
### 2) Add a GitHub token
- Unauthenticated requests are limited to 60/hour. Add a token to raise limits.
- Create .env in the project root:
```
# Vite reads env vars prefixed with VITE_
VITE_GITHUB_TOKEN=ghp_your_token_here
```
### 3) Run dev server
```
npm run dev
```
### 4) Build & preview
```
npm run build
npm run preview
```
---

## 🔗 API Notes
Common endpoints you’ll use:

- Get a user: GET /users/{username}
  Docs: GitHub REST — Users. 

---

## 📁 Project Structure (high level)
```
.
├─ public/
├─ src/
├─ index.html
├─ package.json
└─ vite.config.js
```

---

## 🛣️ Roadmap
- Add repo list + sorting (stars, updated).
- Debounced input + empty/error states.
- Pagination or infinite scroll for large result sets.

---

## 📄 License
MIT — feel free to use and adapt.

---

## 🗣️ Author
Hakim Murphy
