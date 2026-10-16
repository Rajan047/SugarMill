# Sugar Mill Frontend

React + Vite frontend for the Sugar Mill dashboard.

## Run locally

```bash
npm ci
npm run dev
```

Open the Local URL printed by Vite. The development server proxies `/api`
to `http://127.0.0.1:8000`. The Python backend is a separate project and is
not included in this frontend-only export.

## Build

```bash
npm run build
```

Static output is written to `dist/`.

## Deploy on Vercel or Netlify

Import the standalone frontend GitHub repository and use:

| Setting | Value |
| --- | --- |
| Project/root directory | Repository root (`.`) |
| Framework | Vite |
| Install command | `npm ci` |
| Build command | `npm run build` |
| Output/publish directory | `dist` |

If importing the original SugarMill_PipeLine repository instead, set the
project/base directory to `sugarMill`.

Deployment guides:
- https://vercel.com/docs/frameworks/frontend/vite
- https://docs.netlify.com/build/frameworks/framework-setup-guides/vite/

## Frontend-only behavior

Scope & Add-ons includes five illustrative image previews (fire, smoke,
PPE, restricted areas, and bag weight). They are proposed features, not active
models. Theme switching, page navigation, preview dialogs, and concept filters
work without Python.

Live camera connections, bag inference, training, CSV downloads, and production
records require the Python API. The Vite development proxy does not run in a
static deployment. For live operation, the hosting platform must route `/api/*`
to a reachable backend. No backend URL or production API route is configured
in this export. Do not route API requests to the SPA index page.

This export contains no Python code, model checkpoints, datasets, or virtual
environment. Keep `node_modules`, `.env*`, and generated `dist` out of source
control. Only publish the static `dist` contents when doing a manual deployment.
