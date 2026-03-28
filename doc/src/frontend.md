# Frontend

## Overview

The frontend is a React application bootstrapped with Vite. It provides the user interface for creating, reviewing, and filing tax returns.

## Project Layout

```
frontend/
  src/
    components/      # Reusable UI components
    pages/           # Page-level components (routes)
    services/        # API client functions
    hooks/           # Custom React hooks
    context/         # React context providers
    types/           # TypeScript type definitions
    App.tsx          # Root component
    main.tsx         # Entry point
  public/            # Static assets
  package.json
  vite.config.ts
```

## Key Dependencies

- `react` + `react-dom` - UI framework
- `react-router-dom` - Client-side routing
- `axios` - HTTP client
- `typescript` - Type safety

## Pages

| Route                  | Page              | Description                          |
|------------------------|-------------------|--------------------------------------|
| `/`                    | Home              | Dashboard with return list           |
| `/returns/new`         | New Return        | Tax return input form                |
| `/returns/:id`         | Return Detail     | View a single return                 |
| `/returns/:id/review`  | Finish and File   | Review and submit the return         |
| `/returns/:id/print`   | Print             | Printable/downloadable return view   |

## Development

```bash
cd frontend
npm install
npm run dev
```

## Building for Production

```bash
npm run build
```

Output goes to `frontend/dist/`.
