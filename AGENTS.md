# AGENTS.md

Personal homepage (Logist 的个人主页). Vue 3 SPA, content is in Chinese — write UI text and docs in Chinese to stay consistent.

## Commands

- `npm run dev` — Vite dev server (http://localhost:5173)
- `npm run build` — builds to `dist/`
- `npm run preview` — preview the build

There is no test, lint, or typecheck setup. Don't invent one; `npm run build` is the verification step.

## Architecture

- Vue 3 `<script setup>` SFCs, Vite 5, Vue Router 4 (Hash mode). `src/router/index.js` lazily imports views and redirects all unmatched paths to `/`.
- `vite.config.js` sets `base: './'` so the app can deploy to any static path (e.g. GitHub Pages). Keep this; it pairs with the Hash router.
- Views: `src/views/Home.vue`, `src/views/About.vue`. Shared styles live in `src/assets/main.css` (design variables).
- Root component `src/App.vue` renders the router-view and a footer.

## Gotchas

- Project data is maintained in the `projects` array inside `src/views/Home.vue`; the Home page's "项目" stat count derives from `projects.length`. Add/edit projects there, not in templates or other files.
- The footer "广告位招租" ad banner in `src/App.vue` is a deliberately kept element (referenced in README). Don't remove it.
