# Object Detection Notes

Object Detection Notes is a static Zensical website introducing object detection to readers who know basic Python and are new to computer vision. The initial version intentionally contains one article: **Introduction to Object Detection: Bounding Boxes, Models, and Evaluation**.

- Repository: [github.com/qwrtasdfgh/object-detection-notes](https://github.com/qwrtasdfgh/object-detection-notes)
- GitHub Pages URL: [qwrtasdfgh.github.io/object-detection-notes](https://qwrtasdfgh.github.io/object-detection-notes/)

## Local setup on Windows

Run these commands from Anaconda Prompt or PowerShell with Conda initialized.

Create the environment for the first time:

```powershell
conda env create -f environment.yml
```

Update an existing environment after dependencies change:

```powershell
conda env update --name objectdetection-site --file environment.yml --prune
```

Activate it:

```powershell
conda activate objectdetection-site
```

Preview the site at `http://127.0.0.1:8000/`:

```powershell
zensical serve
```

Create a clean static build in `site/`:

```powershell
zensical build --clean
```

Commands can also run without activation, for example:

```powershell
conda run -n objectdetection-site zensical build --clean
```

## Adding pages later

Keep Markdown source files under `docs/`. After creating a real page, add one corresponding entry to the explicit `nav` array in `zensical.toml`. Do not add navigation entries for pages that do not exist. The generated `site/` directory is build output and must not be committed.

## GitHub Pages deployment

The workflow at `.github/workflows/pages.yml` builds the site from source and deploys the generated `site/` directory. Zensical is installed temporarily on the GitHub-hosted runner from the pinned `requirements.txt`; no Conda environment or generated site is committed.

To enable deployment for the repository:

1. Open the repository’s **Settings → Pages**.
2. Under **Build and deployment**, select **GitHub Actions** as the source if it is not already selected.
3. Push to `main` or manually run the **Deploy Zensical site to Pages** workflow.
4. Follow the deployment URL shown in the workflow’s `github-pages` environment.

The configured `site_url` is the GitHub Pages URL. Keep it until a custom domain is configured, then update it and verify the generated canonical link and sitemap.
