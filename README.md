# cloudflare

This repository contains Cloudflare Workers deploy targets.

## Apps Worker

The `apps` folder is a minimal static site deployed as a Cloudflare Worker with
Static Assets.

Cloudflare Worker settings:

- Worker name: `apps`
- Root directory: repository root
- Build command: leave empty
- Deploy command: `npx wrangler deploy`
- Static assets directory: `apps`
- Custom domain: `apps.jeremyxie.com`

The root `wrangler.toml` points Cloudflare Workers at the `apps` directory and
binds the Worker to the custom domain.

## Automatic Deployment

GitHub Actions deploys the Worker automatically when changes are pushed to
`main` under `apps/**`, `wrangler.toml`, or the deployment workflow itself.

Required GitHub repository secrets:

- `CLOUDFLARE_ACCOUNT_ID`
- `CLOUDFLARE_API_TOKEN`

The workflow is defined in `.github/workflows/deploy-worker.yml`.

For a local dry run:

```sh
npx wrangler deploy --dry-run
```

For manual deployment with Wrangler:

```sh
npx wrangler deploy
```

Manual Wrangler deploys require `wrangler login` or a `CLOUDFLARE_API_TOKEN`
environment variable.
