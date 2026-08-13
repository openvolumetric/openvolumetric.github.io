# OpenVolumetric website

The OpenVolumetric project website, built with Jekyll and hosted on GitHub Pages.

## Run locally

1. Install Ruby 3.x and Bundler (avoid the older macOS system Ruby).
2. Run `bundle install`.
3. Run `bundle exec jekyll serve`.
4. Open <http://localhost:4000>.

### Run with Docker

The legacy Sass compiler included in some Jekyll images needs an explicit UTF-8
locale. From the repository root, run:

```sh
docker run --rm -it \
  --mount type=bind,source="$(pwd)",target=/data \
  -p 4000:4000 \
  -e LANG=C.UTF-8 \
  -e LC_ALL=C.UTF-8 \
  jekyll
```

Then open <http://localhost:4000>. The `faraday-retry` message printed by that image is a warning and does not prevent the site from building.

Content lives in `index.md`, shared project data in `_data`, and the visual system in
`assets/css/main.css`.

## Publish

In the repository's GitHub Pages settings, choose **Deploy from a branch**, select
`main`, and use the repository root (`/`). GitHub Pages will build the Jekyll site
whenever changes land on `main`.
