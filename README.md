# cloudflare

This repository contains Cloudflare deploy targets.

## Apps Pages

The `apps` folder is a minimal static site that can be deployed directly with
Cloudflare Pages.

Cloudflare Pages settings:

- Project name: `apps`
- Root directory: `apps`
- Build command: leave empty
- Build output directory: `.`
- Build watch paths include: `apps/**`

With those settings, commits that change files under `apps/` trigger the
Cloudflare Pages deployment for the `apps` project.

For manual deployment with Wrangler:

```sh
npx wrangler pages deploy apps --project-name apps
```
