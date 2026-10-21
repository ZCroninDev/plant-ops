# Plant Ops

An operations app for a **fictional** wastewater treatment plant: shift scheduling, operator rounds, lab results, compliance reports, and work orders.

The plant, the operators, and every reading are made up. No real facility or personal data is used.

The app is built and tested to Section 508 and WCAG 2.2 AA accessibility standards.

## Status

In early development. See the [issues](../../issues) for current work.

## Tech stack

| Layer | Choice |
|---|---|
| Front end | Angular 22, TypeScript (strict), standalone components, signals |
| API | Node, Express, TypeScript (a second implementation in ASP.NET Core is planned) |
| Database | SQL Server with hand-written, parameterized T-SQL (no ORM) |
| Tests | Angular CLI test runner, Vitest and Supertest for the API, Playwright with axe-core for end-to-end and accessibility checks |
| CI | GitHub Actions |

## Project structure

```
client/        Angular app
server/        Express API
db/
  migrations/  numbered .sql files that build the schema
  seed/        fake data
  queries/     report queries, each with a comment explaining it
```

## Prerequisites

- Node.js 22 or newer
- SQL Server Developer Edition (free) and a SQL client such as SSMS, Azure Data Studio, or the VS Code SQL Server extension

## Getting started

### Client

```
cd client
npm install
npm start
```

The app runs at http://localhost:4200.

Run the tests with `npm test`.

### Database

1. Install SQL Server Developer Edition and enable TCP/IP on port 1433.
2. Create the database: `CREATE DATABASE plant_ops;`
3. Copy `server/.env.example` to `server/.env` and fill in your local connection details. The `.env` file is ignored by git.
4. Test the connection in your SQL client with `SELECT @@VERSION;`.

### API

Setup steps for `server/` will be added as it is built.

## Decisions

This section will be filled in as the project grows.

## Accessibility

Notes from keyboard-only and screen reader testing, and the Accessibility Conformance Report, will be added here.
