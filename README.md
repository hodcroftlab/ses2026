# ses2026 (Jekyll site)

This is a minimal, single-page conference site for the **1st Swiss Enterovirus Symposium**.

## Local run (Ruby 3.2 via micromamba)

Create a micromamba environment with Ruby 3.2 and the neccessary compilers and activate it
```bash
micromamba create -n jekyll-ses -c conda-forge ruby=3.2 make gcc_linux-64 gxx_linux-64 pkg-config openssl libffi zlib jemalloc

micromamba activate jekyll-ses
```

Clone the repository:
```bash
git clone git@github.com:hodcroftlab/ses2026.git
cd ses2026
```

Install gems only locally in the directory, then install bundler and gems needed
```bash
bundle config set path 'vendor/bundle'
bundle install
```

And serve the website locally:
```bash
bundle exec jekyll serve
```

Then open: http://127.0.0.1:4000/ses2026/

## GitHub Pages

This repo includes a GitHub Actions workflow at `.github/workflows/pages.yml` which builds and deploys the site to GitHub Pages.

### Important settings
- `_config.yml` is set for **hodcroftlab/ses2026**:
  - `url: https://hodcroftlab.github.io`
  - `baseurl: /ses2026`

If you later move to a custom domain, update `url` and `baseurl` accordingly.

## Editing content

### Registration URL
Edit this in `_config.yml`:

```yml
event:
  registration_url: "#"
```

### Speakers
Edit `_data/speakers.yml`. Cards render automatically.

Speaker images live at `assets/img/speakers/*.png`. Placeholders are included; you can overwrite them with real headshots.

### Program table
Edit `_data/program.yml`. The table is generated from structured YAML.

### Abstract deadline banner (on/off)
Toggle this in `_config.yml`:

```yml
event:
  abstract_submission:
    enabled: true   # set false to hide
    deadline: "TBD"
    url: "#"
```

### Sponsors
Edit `_data/sponsors.yml`. Add `logo:` and `url:` when ready.

## Assets
- Hero image: `assets/img/hero.jpg`
- Speaker headshots: `assets/img/speakers/`
