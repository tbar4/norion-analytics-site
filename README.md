# norion-analytics-site

The [norionanalytics.com](https://norionanalytics.com) site — [Hugo](https://gohugo.io/),
published to GitHub Pages by `.github/workflows/deploy.yml` on every push to `main`.

## Theme

[`imgios/not-much`](https://github.com/imgios/not-much), vendored at tag `0.21.0`
(commit `b251d1a`) under `themes/not-much/` rather than tracked as a submodule, so
the CI checkout needs no extra steps. Theme options are documented in
`themes/not-much/configuration.md`; the site-level knobs live in `hugo.toml`.

To update the theme, replace the contents of `themes/not-much/` with a newer
checkout (excluding its `.git`, `.github`, `exampleSite` and `images`) and note
the new version here.

## Local development

Hugo **extended** ≥ 0.146 is required — the theme uses the `layouts/_partials/`
template layout introduced in that release. CI pins 0.158.0.

```shell
hugo server -D               # http://localhost:1313, drafts included
hugo new content posts/my-post.md
hugo --gc --minify           # production build into public/
```
