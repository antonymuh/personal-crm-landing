# Лендинг «Личная CRM»

Одна статичная страница: Astro + Tailwind CSS 4. Кнопки ведут в приложение https://app.pocketcrm.co.

- Макет из Claude Design: `design/landing.html`
- Цвета, шрифты, размеры: `src/styles/tokens.css`
- Страница: `src/pages/index.astro`
- Шрифты (Unbounded, Golos Text, Caveat, лицензия OFL) лежат в `public/fonts/`

## Запуск у себя

```
pnpm install
pnpm dev
```

Откроется http://localhost:4321

## Сборка

`pnpm build` собирает готовую страницу в папку `dist/`.

## Выкатка

Push в `main` → GitHub Actions собирает `dist/` → `rsync --delete` в `/var/www/pocketcrm-landing` на сервере → проверка, что https://pocketcrm.co отвечает. Ход выкатки — вкладка Actions репозитория.

Настройки в GitHub: секреты `DEPLOY_SSH_KEY`, `DEPLOY_KNOWN_HOSTS`; переменные `DEPLOY_HOST`, `DEPLOY_USER`, `SITE_URL`.
