# ePlus OnAir — PR Previews

This repository hosts generated, temporary static previews for pull requests from [ePlus-DEV/radio.eplus.dev](https://github.com/ePlus-DEV/radio.eplus.dev).

- Source: GitHub Actions in the source repository; feature and fix PRs target **`staging`**
- Published output branch: `main` in this repository (GitHub Pages: `/(root)`)
- Custom domain: https://preview.radio.eplus.dev (root `CNAME` must stay intact)
- Previews: `pr-preview/pr-<number>/`
- GitHub Environment: `preview` for trusted publishing and cleanup, activated with repository Actions Variable `PAGES_PREVIEW_READY=true` after provisioning (documented legacy `development` fallback during migration).
- Preview **build jobs are untrusted and receive no deploy credentials**; only separate trusted publish/cleanup jobs access a scoped `PAGES_DEPLOY_TOKEN`.
- Staging application: https://stg.radio.eplus.dev (`staging` branch); Production: https://radio.eplus.dev (`main` branch).
- Previews are `noindex`, do not publish a production sitemap/canonical/JSON-LD, and must not emit production GA4.
- No application source or secrets belong here.
- A Preview link is shown in its source PR only after public HTML, `noindex` and exact `preview-commit.txt` head SHA are verified. It is hidden while rebuilding or on failure.
- Preview directories are automatically removed after their PR closes.
- The repository root `404.html` is a non-indexed, client-side fallback. For an unavailable route such as `/pr-preview/pr-375/global-radio/apple-music/`, it displays a **5-second countdown** and redirects to `https://radio.eplus.dev/global-radio/apple-music/` (including query string and fragment). Unknown/non-PR paths fall back to the production homepage. The user can open the target immediately. GitHub Pages still responds with HTTP **404**, not a 301/302.
- Keep the root `CNAME`, `404.html`, `index.html`, and `.nojekyll` when publishing or cleaning up a PR preview. Only sync/delete the specific `pr-preview/pr-<number>/` directory.

Do not edit generated preview files manually.
