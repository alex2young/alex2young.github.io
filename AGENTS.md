# Repository Guidelines

## Project Structure

- Root pages: `index.html`, `about.md`, `archive.html`, `404.html`.
- Posts: `_posts/YYYY-MM-DD-title.md`.
- Theme: `minimal-mistakes-jekyll` gem; avoid local theme overrides unless needed.
- Data: `_data/navigation.yml`.
- Includes: `_includes/footer.html` keeps the footer minimal.
- Styles: `_sass/_site.scss` and `assets/css/main.scss` contain the local visual layer.
- Assets: `assets/` for favicons, images, and standalone static files.
- GitHub Pages workflow: `.github/workflows/pages.yml`.
- Docker configs: `docker/`.

## Commands

- `export PATH="/opt/homebrew/opt/ruby/bin:$PATH"`: use the Ruby version in `.ruby-version`.
- `BUNDLE_PATH=vendor/bundle BUNDLE_USER_HOME=.bundle BUNDLE_FORCE_RUBY_PLATFORM=true bundle install`: install Ruby dependencies locally.
- `npm install`: install Node tooling.
- `npm run serve`: run the local Jekyll site.
- `npm run build`: build the production site.
- `npm audit`: check Node tooling dependencies.
- `npm run docker-dev:serve`: start the Docker Compose dev setup.

## Style

Follow `.editorconfig`: UTF-8, LF, two-space indentation, final newline, no
trailing whitespace, and 80-character preferred lines. Keep Markdown front
matter valid YAML. Prefer gem-theme configuration over copying theme internals
into this repository. Keep custom styling in `_sass/_site.scss`.

## Checks

There is no broad unit-test suite. Before submitting changes, run the checks
that match your edit:

- Content/config: `npm run build`.
- Dependency changes: `npm audit`.
- Visual or route changes: `npm run serve`, then inspect affected pages.

## Commits & PRs

Use Conventional Commits: `type(scope): subject`. Preferred types include
`feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, and `release`.
Keep subjects lowercase, under 72 characters, and without a period.

PRs should include a short change summary, verification commands, linked issues
when relevant, and screenshots for layout, styling, or image changes.
