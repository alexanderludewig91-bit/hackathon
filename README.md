# Hackathon Hallo-Welt Starter

Minimaler Ausgangspunkt für lokale Hackathon-Prototypen mit Node 20+, Express und SQLite.

## Setup

1. Node 20 installieren.
   - Windows: https://nodejs.org/dist/v24.11.0/node-v24.11.0-x64.msi
   - Mac: https://nodejs.org/dist/v24.11.0/node-v24.11.0.pkg
2. Terminal/PowerShell öffnen und ins Projektverzeichnis wechseln.
   - Windows: Startmenü → „PowerShell“. Dann `cd C:\Users\<Name>\hackathon`.
   - Mac: Spotlight → „Terminal“. Dann `cd ~/hackathon`.
3. `npm install`
4. `.env` anpassen, falls andere Ports/DB-Pfade benötigt werden.

## Entwicklung

Alle folgenden Befehle laufen im selben Fenster wie `npm install`.

```bash
npx prisma db push
npm run dev
```

Server startet standardmäßig auf `http://localhost:3000`.

## Tests

Für Tests gilt das gleiche Terminal (Windows & Mac identische Befehle):

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

