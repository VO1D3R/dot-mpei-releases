# DOT МЭИ — Releases

Здесь лежат только подписанные Mozilla сборки расширения и `updates.json`
(манифест автообновления). Исходный код сюда не выкладывается.

- `dot-mpei.xpi` — последняя подписанная версия.
- `updates.json` — отсюда Firefox/Zen узнают о новых версиях,
  адрес прописан в расширении как `browser_specific_settings.gecko.update_url`.

## Как выпустить обновление

1. Поднять `version` в `extension/manifest.json`.
2. `.\build.ps1` — обновит `dist/updates.json`.
3. Подписать: `npx web-ext sign --channel=unlisted --api-key=... --api-secret=...`
4. Скачать подписанный `.xpi` из Центра разработчиков, переименовать в `dot-mpei.xpi`.
5. Положить сюда `dot-mpei.xpi` и свежий `updates.json`, закоммитить и запушить.
