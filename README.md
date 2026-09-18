# Object Detection Notes

Object Detection Notes is a static Zensical website introducing object detection to readers who know basic Python and are new to computer vision. The initial version intentionally contains one article: **Introduction to Object Detection: Bounding Boxes, Models, and Evaluation**.

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

## Publishing status

GitHub and GitHub Pages are not configured yet. When the final GitHub username or custom domain is known, set `site_url` in `zensical.toml` before deployment so Zensical can emit the correct canonical URL and sitemap entries.
