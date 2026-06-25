# tasklist-backend

Backend Node.js/TypeScript pour une application de gestion de tâches.

## Description

Ce projet expose une API REST pour gérer des tâches. Il utilise Express, Prisma et une architecture de services/controllers/routes.

## Prérequis

- Node.js 18+ ou compatible
- npm
- Docker
- Trivy

## Installation

```bash
npm ci
npm run prisma:generate
```

## Exécution en développement

```bash
npm run dev
```

## Build

```bash
npm run build
```

## Tests

### Tests unitaires

```bash
npm run test
```

### Tests de couverture

```bash
npm run test:coverage
```

### Tests E2E

```bash
npm run test:e2e
```

### Couverture E2E

```bash
npm run test:e2e:coverage
```

## Politique de couverture

La configuration Vitest impose des seuils de couverture afin de détecter les régressions :

- statements: 80%
- branches: 80%
- functions: 80%
- lines: 80%

## Docker

Pour construire l'image Docker locale :

```bash
docker build -t tasklist-backend:latest .
```

Pour exécuter l'image :

```bash
docker run -p 3000:3000 -e DATABASE_URL="<your_database_url>" tasklist-backend:latest
```

## Fichiers importants

- `src/` : code source
- `src/controllers/` : contrôleurs Express
- `src/services/` : logique métier
- `src/routes/` : définition des routes
- `src/lib/prisma.ts` : client Prisma
- `vitest.config.ts` : configuration des tests et de la couverture
- `Dockerfile` : build d'image Docker
- `.dockerignore` : fichiers exclus de l'image Docker
- `runbooks/` : incidents et procédures d'exploitation

## Runbook incident couverture

Un runbook est disponible pour le cas d'une chute critique de la couverture de code :

- `runbooks/coverage-drop-runbook.md`

## Notes

- N'ajoutez jamais de fichiers sensibles comme `.env` au dépôt.
- Utilisez `.dockerignore` pour éviter d'inclure des artefacts locaux dans l'image Docker.
- Si vous modifiez la logique métier, ajoutez les tests nécessaires pour maintenir la couverture.
