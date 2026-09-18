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

## Publishing placeholder

`zensical.toml` documents `https://YOUR_GITHUB_USERNAME.github.io/object-detection-notes/` as a commented placeholder. Replace it and enable `site_url` only after the GitHub account and final domain are known.

## SEO and publishing limitations

- The final public domain is not known, so `site_url` is documented but intentionally commented out in `zensical.toml`.
- Without `site_url`, Zensical 0.0.62 does not emit a canonical link and generates an empty `sitemap.xml`. This avoids publishing the placeholder as a fake production URL.
- Before deployment, set `site_url` to the real GitHub Pages or custom-domain URL, rebuild, and verify both the canonical link and populated sitemap.
- `robots.txt` explicitly allows crawling, and the rendered page contains no `noindex` or `nofollow` directive.
- No analytics or third-party tracking is configured.
