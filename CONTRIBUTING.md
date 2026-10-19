# Cómo trabajamos

Esta guía aplica a todos los repositorios de RouteEV.

## Flujo

1. Nada se sube directo a `main`: cada cambio va en una **rama** (`feat/...`, `fix/...`, `chore/...`).
2. Abrí un **Pull Request** contra `main` y describí qué cambia y cómo lo probaste.
3. Se mergea solo con el **CI en verde**. En el frontend, además, revisá la vista previa de Vercel que aparece en el PR.
4. Commits en español, en imperativo y con prefijo: `feat:`, `fix:`, `perf:`, `docs:`, `chore:`, `ci:`.

## Antes de abrir el PR

- **Frontend:** `npm run lint`, `npm test` y `npm run build` (el build corre `tsc -b`, que también typechequea los tests).
- **Backend:** `pytest` contra una base de pruebas (`TEST_DATABASE_URL`), **nunca** contra producción. Ver el README del repo.

## Datos y secretos

- Nunca subas claves, tokens ni archivos `.env`. Usá los `.env.example`.
- Los datos de prueba no van a la base de producción.

## Deploy

- Frontend: Vercel publica cada merge a `main` en [routeev.uy](https://routeev.uy).
- Backend: el deploy al servidor es manual. Avisá en el grupo cuando mergees algo del backend.
