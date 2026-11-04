# Schedule Builder POC v2

A working full-stack proof of concept for shared editorial scheduling across X1, Xfinity XSB, and Stream.

## Requirements
- Node.js 18 or newer
- No npm packages or external database are required

## Start
```bash
npm start
```
Open http://localhost:3000

For automatic server restarts during development:
```bash
npm run dev
```

## What is implemented
- Node.js HTTP server
- REST API
- Server-side JSON database at `data/db.json`
- Seeded fictional schedule data
- Create and edit schedule entries
- Entry detail view with all editorial/programming fields
- Automatic conflict detection based on platform, placement, and overlapping time windows
- Conflict resolution with decision notes and audit event
- Approval and programming workflow
- QA flagging
- Role switcher for Editor, Operations, QA, and Executive
- Operator programming queue
- Executive summary
- Activity history
- CSV export

## API
- `GET /api/state`
- `POST /api/entries`
- `PUT /api/entries/:id`
- `POST /api/entries/:id/action`
- `POST /api/conflicts/:id/resolve`
- `GET /api/export.csv`
- `POST /api/reset`

## Reset the demo
Use **Reset demo data** in the UI, or delete `data/db.json` and restart the server.

## POC boundaries
This uses a file-backed database to remain immediately runnable. It proves the shared server workflow, but production should use PostgreSQL, Microsoft Entra ID, role claims, HTTPS, and a deployment target such as Azure App Service or Azure Container Apps.
