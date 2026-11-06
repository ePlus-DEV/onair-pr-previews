# ePlus OnAir — PR Previews

This repository hosts generated, temporary static previews for pull requests from [ePlus-DEV/radio.eplus.dev](https://github.com/ePlus-DEV/radio.eplus.dev).

- Source: GitHub Actions in the source repository
- Branch: `main` (GitHub Pages: `/(root)`)
- Custom domain: https://preview.radio.eplus.dev (root `CNAME` must stay intact)
- Previews: `pr-preview/pr-<number>/`
- No application source or secrets belong here.
- Preview directories are automatically removed after their PR closes.
- The repository root `404.html` is a non-indexed, client-side fallback. For an unavailable route such as `/pr-preview/pr-375/global-radio/apple-music/`, it displays a **5-second countdown** and redirects to `https://radio.eplus.dev/global-radio/apple-music/` (including query string and fragment). Unknown/non-PR paths fall back to the production homepage. The user can open the target immediately. GitHub Pages still responds with HTTP **404**, not a 301/302.
- Keep the root `CNAME`, `404.html`, `index.html`, and `.nojekyll` when publishing or cleaning up a PR preview. Only sync/delete the specific `pr-preview/pr-<number>/` directory.

Do not edit generated preview files manually.
