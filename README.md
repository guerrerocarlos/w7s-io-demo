# w7s-io-demo

Small W7S deployment demo with a bundled Hono backend and a built React frontend.

Layout:

- `backend/src/index.ts`: Hono Worker source.
- `backend/index.js`: generated backend bundle deployed by W7S.
- `frontend/src`: React frontend source.
- `frontend/dist`: generated static frontend served before backend fallback.
- `.github/workflows/deploy.yml`: deploys this repo with the reusable W7S deploy action.

The generated deploy artifacts are intentionally ignored by git. The deploy workflow runs:

```sh
npm ci
npm run build
```

before the W7S action packages the repo.

Local commands:

```sh
npm install
npm run check
npm run dev
```

After deployment, the app URL is:

```text
https://guerrerocarlos.w7s.cloud/w7s-io-demo/
```

The public wildcard route must point at the new `w7s-io` core Worker for that URL to resolve.
