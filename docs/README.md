# Documentation site (Astro + Starlight)

This folder is the Astro project root for the published documentation site.

- Content lives under `src/content/docs/` and is organised by AUTOSAR layer.
- Site configuration is in `astro.config.mjs`. The GitHub Pages `site` and `base` URLs are derived automatically from the `origin` remote (or the `GITHUB_REPOSITORY` environment variable); no owner or repository name is hard-coded, so forks keep working.
- Converted design documents sit next to their module page (e.g. `application-software/SteeringPowerAssistControl/doc-*.md`) and are hidden from the sidebar but linked from the module page.

## Local preview

```sh
npm install
npm run dev
```

## Production build

```sh
npm install
npm run build
```

The static site is emitted to `dist/`.
