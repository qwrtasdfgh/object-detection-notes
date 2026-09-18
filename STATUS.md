# Project status

## Current state

- Initial one-page Zensical site scaffolded.
- Introductory article and original labeled street-scene figure completed.
- GitHub and GitHub Pages intentionally not configured yet.

## Tested toolchain

- Conda environment: `objectdetection-site`
- Python: 3.10.20
- Zensical: 0.0.62

Zensical 0.0.62 requires Python 3.10 or newer. Python 3.10 was selected because a compatible local Conda interpreter was available without relying on the host's currently failing Conda repository proxy.

## Verification

Completed on 2026-09-18:

- `conda run -n objectdetection-site zensical --version` returned `0.0.62`.
- `conda run -n objectdetection-site zensical build --clean` completed with `No issues found`.
- `site/index.html` was generated.
- Theme CSS, JavaScript, image, logo, favicon, search, and sitemap assets were generated under `site/`.
- The explicit configuration contains exactly one navigation item: `Introduction to Object Detection` → `index.md`.

The host's Conda 22.9 repository connection failed with TLS/proxy errors during environment solving. To complete the local test without changing persistent Conda settings, the requested environment was created by cloning an existing local Python 3.10 Conda environment, after which Zensical 0.0.62 was installed with pip successfully. `environment.yml` remains the clean, reproducible specification for a normally connected machine.

## Publishing URL

`site_url` is set to `https://qwrtasdfgh.github.io/object-detection-notes/`. Keep this GitHub Pages URL until a custom domain is configured.

## SEO and publishing limitations

- The GitHub Pages URL is configured, so Zensical emits a canonical link and populated sitemap. Update `site_url` if a custom domain is configured later.
- `robots.txt` explicitly allows crawling, and the rendered page contains no `noindex` or `nofollow` directive.
- No analytics or third-party tracking is configured.
