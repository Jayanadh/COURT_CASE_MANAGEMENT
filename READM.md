# ⚖️ CourtWise Harmony — Court Case Management

[![Vite](https://img.shields.io/badge/Vite-React%2FTS-646CFF)](https://vitejs.dev/) 
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.x-38B2AC)](https://tailwindcss.com/) 
[![Firebase](https://img.shields.io/badge/Firebase-Auth%20%7C%20Firestore-FFCA28)](https://firebase.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Modern, role‑aware court case management for lawyers, clients, and court staff — built with **React + TypeScript + Vite**, styled with **Tailwind & shadcn/ui components**, and powered by **Firebase** for auth and data.

> Repo: `jithsungh/Court_Case_Management` (Vite + TS with Tailwind, Bun lockfile present).

---

## ✨ Features

- **Cases & Dockets**: create, view, and manage cases with role‑specific views (plaintiff, defense, clerk).  
- **Scheduling**: flexible calendar for hearings and court events.  
- **Messaging**: secure conversation between parties (client‑lawyer, lawyer‑clerk).  
- **Discovery**: find lawyers and check cases filed against you.  
- **Profiles & Auth**: email/password auth, profile management via Firebase.  
- **Docs & Pages**: How it works, FAQ, Help Center, and legal policies (T&C, Privacy, Cookies, GDPR).  

---

## 🧱 Tech Stack

- **Frontend**: React 18, TypeScript, React Router, Vite.  
- **Styling**: Tailwind CSS, shadcn/ui patterns (clsx, tailwind‑merge, class‑variance‑authority), CSS Modules.  
- **Backend / Data**: Firebase (Auth + Firestore).  
- **Tooling**: Bun (lockfile), or NPM. ESLint, PostCSS, Autoprefixer, Tailwind.  

---

## 📂 Project Structure (high level)

```
/public               # static assets
/src
  /components         # reusable UI (incl. shadcn-style components in components/ui)
  /context            # React Context providers (Auth, App data)
  /data               # static/mock datasets (seed JSON, etc.)
  /firebase           # firebase config & helpers
  /hooks              # custom hooks
  /integrations       # external services (e.g., Supabase if used)
  /lib                # utils (e.g., cn() className helper)
  /models             # data models
  /pages              # route-mapped pages
  /services           # domain logic (notifications, etc.)
  /types              # TS types
  /utils              # misc utilities (formatters, validators)
  App.tsx / main.tsx  # app entry & routing
tailwind.config.ts
postcss.config.js
vite.config.ts
package.json
bun.lockb
```

---

## 🚀 Getting Started

### 1) Clone
```bash
git clone https://github.com/jithsungh/Court_Case_Management.git
cd Court_Case_Management
```

### 2) Install deps (choose one)
Using **Bun** (recommended if you have it):
```bash
bun install
```
Using **npm**:
```bash
npm install
```

### 3) Firebase setup
Create a Firebase project and enable **Authentication** and **Firestore**.  
Add your web app config as `src/firebase/config.ts` (and keep it out of git):

```ts
// src/firebase/config.ts
export const firebaseConfig = {
  apiKey:        import.meta.env.VITE_FIREBASE_API_KEY,
  authDomain:    import.meta.env.VITE_FIREBASE_AUTH_DOMAIN,
  projectId:     import.meta.env.VITE_FIREBASE_PROJECT_ID,
  storageBucket: import.meta.env.VITE_FIREBASE_STORAGE_BUCKET,
  messagingSenderId: import.meta.env.VITE_FIREBASE_MESSAGING_SENDER_ID,
  appId:         import.meta.env.VITE_FIREBASE_APP_ID,
};
```

Create a `.env` (or `.env.local`) with your keys:
```bash
VITE_FIREBASE_API_KEY=...
VITE_FIREBASE_AUTH_DOMAIN=...
VITE_FIREBASE_PROJECT_ID=...
VITE_FIREBASE_STORAGE_BUCKET=...
VITE_FIREBASE_MESSAGING_SENDER_ID=...
VITE_FIREBASE_APP_ID=...
```

### 4) Run
```bash
# Bun
bun run dev

# or npm
npm run dev
```
Open: http://localhost:5173

### 5) Build & Preview
```bash
# build
bun run build   # or: npm run build

# preview production build
bun run preview # or: npm run preview
```

---

## 🧪 Scripts (common)
- `dev` — start Vite dev server  
- `build` — production build to `dist/`  
- `preview` — serve the built app locally  
- `lint` — run eslint (if configured in `package.json`)  

---

## 🔐 Environment & Secrets
- Do **not** commit real Firebase keys; use `.env` and reference via `import.meta.env`.  
- Add `src/firebase/config.ts` to `.gitignore` if it contains literals.  

---

## 📦 Dependencies (high level)

> Install via `bun install` or `npm install`. See `requirements.txt` in this repo for a quick list (reference only). The canonical source of truth remains `package.json`.

- **Runtime**: `react`, `react-dom`, `react-router-dom`, `firebase`  
- **Styling/UI**: `tailwindcss`, `postcss`, `autoprefixer`, `clsx`, `tailwind-merge`, `class-variance-authority`, `lucide-react`, `@radix-ui/react-icons`  
- **Build/Types**: `vite`, `@vitejs/plugin-react-swc`, `typescript`, `@types/react`, `@types/react-dom`  
- **Lint**: `eslint`, `@typescript-eslint/parser`, `@typescript-eslint/eslint-plugin`  

---

## 🤝 Contributing
1. Fork → feature branch → commit with conventional messages → PR.  
2. Add tests or minimal repro where applicable.  
3. Run `lint` and ensure build passes before pushing.

---

## 📄 License
MIT — see `LICENSE` (add one if not present).

---

## 📚 Acknowledgements
- Vite React + TS starter, TailwindCSS, shadcn/ui patterns.  
- Firebase Auth & Firestore.

