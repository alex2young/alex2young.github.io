# alex2young.github.io

Personal Jekyll site published at <https://alex2young.github.io>.

## Structure

- `_posts/`: published posts using `YYYY-MM-DD-title.md` filenames.
- `_data/navigation.yml`: Minimal Mistakes navigation.
- `_includes/footer.html`: minimal footer override.
- `_sass/_site.scss`: local visual entry point for focused Sass partials in
  `_sass/site/`.
- `assets/css/main.scss`: theme stylesheet entry point plus local styles.
- `assets/`: favicons, images, vendored browser scripts, and static assets.
- `pages/`: standalone pages outside the main post flow.
- `.github/workflows/pages.yml`: build, check, and deploy GitHub Pages.
- `docker/`: optional local Docker build and serve configuration.

## Development

Install dependencies:

```sh
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
BUNDLE_PATH=vendor/bundle BUNDLE_USER_HOME=.bundle BUNDLE_FORCE_RUBY_PLATFORM=true bundle install
npm install
```

Run locally:

```sh
npm run serve
```

Build for production:

```sh
npm run build
```

Run targeted checks:

```sh
npm audit
```

## Docker

Build the development image, then serve the site:

```sh
npm run docker-dev:build-image
npm run docker-dev:serve
```

## Notes

This site uses the `minimal-mistakes-jekyll` gem theme with a small editorial
style layer split across `_sass/site/`. Keep local overrides narrow and note
the upstream theme version in copied includes so theme updates remain
straightforward.

GitHub Pages is deployed through Actions so the site can use third-party
gem-packaged themes.
