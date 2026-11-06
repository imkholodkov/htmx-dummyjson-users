# htmx + Mustache: список пользователей из dummyjson

Клик по ссылке — htmx (`hx-get`) запрашивает `https://dummyjson.com/users?limit=5&select=email,password`,
расширение `client-side-templates` прогоняет JSON-ответ через шаблон Mustache из `<template>`,
готовый HTML подставляется в `#users` (`hx-target`). Своего JavaScript нет — только атрибуты.

Почему так: htmx ждёт от сервера HTML, а dummyjson отдаёт JSON; расширение `client-side-templates`
с Mustache превращает JSON в HTML на клиенте, поэтому сервер не нужен и хватает GitHub Pages.
`selfRequestsOnly: false` в `htmx-config` разрешает htmx 2 запрос на чужой домен (CORS у dummyjson открыт).

Размещение: Settings → Pages → Deploy from branch → `main` / root.
