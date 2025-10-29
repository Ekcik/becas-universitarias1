
# Becas Universitarias 2.0

Proyecto universitario: registro de becas con confirmación por correo/WhatsApp y panel administrativo.

## Stack
- Next.js + TypeScript (App Router)
- Prisma ORM (SQLite dev / Postgres prod)
- NextAuth (credenciales) para admin
- Playwright para E2E
- CI en GitHub Actions

## Arquitectura
- **Formulario 3 pasos**: `/registro`
- **API solicitudes**: `POST/GET /api/solicitudes`
- **Panel admin**: `/admin` (requiere login)
- **Auth**: `app/api/auth/[...nextauth]/route.ts` (credenciales)

## Setup local
```bash
npm i
cp .env.example .env
npm run prisma:push
npm run dev
```
Abrir http://localhost:3000

## Variables de entorno
Ver `.env.example`

## Sprints y roles
- PO/PM: Damian
- SM/BE: Natalia
- FE: Yesica
- QA: Melanie
- Integraciones: Miguel

## Rutas
- `/registro`: formulario 3 pasos
- `/admin`: panel con filtros (solo admin)
- `/api/solicitudes`: POST/GET

## Tests
```bash
npm run test:e2e
```

## Deploy
- Configurar `DATABASE_URL`, secretos de NextAuth y servicios (SMTP/WhatsApp).
- Vercel/Render/Railway.

---

### Roadmap (resumen)
- Sprint 1: Registro + email
- Sprint 2: Tipos de beca + WhatsApp
- Sprint 3: Panel admin
- Sprint 4: Auth admin + E2E + informe
# becas-universitarias1
