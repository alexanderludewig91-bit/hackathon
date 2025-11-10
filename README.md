# Hackathon Hallo-Welt Starter

Minimaler Ausgangspunkt für lokale Hackathon-Prototypen mit Node 20+, Express und SQLite.

## Setup

1. Node 20 installieren.
2. `npm install`
3. `.env` aus `env.example` ableiten (Datei umbenennen) und falls nötig anpassen.

## Entwicklung

```bash
npx prisma db push
npm run dev
```

Server startet standardmäßig auf `http://localhost:3000`.

## Tests

```bash
npm test
```

## Features

- API-Routen:
  - `GET /api/hello` – erster Grüßeintrag aus SQLite
  - `GET /api/messages` – Liste aller Messages
  - `POST /api/messages` – neuen Eintrag anlegen
  - `GET /api/messages/simulate-error` – Fehlerfall demonstrieren
- Frontend: Single-Page-Landing mit Fetch, Formular & Modal-Dialog.
- Fehlerrückgaben im `{ error }`-Format, Logging mit Präfix.
- Prisma Studio optional starten: `npm run prisma:studio`

## Datenbank

- SQLite-Datei `dev.db`
- Prisma-Schema in `prisma/schema.prisma`
- Schema ausrollen via `npx prisma db push` (oder eigene Migrationen)
## Lizenz

MIT

