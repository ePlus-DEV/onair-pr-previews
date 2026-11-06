# ePlus OnAir — PR Previews

This repository hosts generated, temporary static previews for pull requests from [ePlus-DEV/radio.eplus.dev](https://github.com/ePlus-DEV/radio.eplus.dev).

- Source: GitHub Actions in the source repository
- Branch: `main` (GitHub Pages: `/(root)`)
- Custom domain: https://preview.radio.eplus.dev (root `CNAME` must stay intact)
- Previews: `pr-preview/pr-<number>/`
- No application source or secrets belong here.
- Preview directories are automatically removed after their PR closes.
- The repository root `404.html` is a non-indexed, client-side fallback that sends missing/expired preview links to [production](https://radio.eplus.dev/). GitHub Pages still returns HTTP 404 (not 301/302), and this only works once the Pages site is available.
- Keep the root `CNAME`, `404.html`, `index.html`, and `.nojekyll` when publishing or cleaning up a PR preview. Only sync/delete the specific `pr-preview/pr-<number>/` directory.

Do not edit generated preview files manually.
