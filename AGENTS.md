# Working on this site

This is the Great Southern Software company site: a Quarkus Roq static site in the older
Roq layout, everything under `src/main/resources/`. Keep it that way.

- Pages live in `src/main/resources/content/` (`index.html`, `404.html`; front matter +
  HTML), the layout in `src/main/resources/templates/layouts/default.html`, styles in
  `src/main/resources/public/css/`, fonts in `public/fonts/`, images in `public/assets/`.
- `src/main/resources/public/CNAME` holds the custom domain and MUST stay: GitHub Pages reads
  it from the published output. `site.url` in `application.properties` matches it.
- Links use `{site.url('/path')}`; never hard-code the domain. Qute expressions here use the
  default `{expr}` syntax (check `quarkus.qute.alt-expr-syntax` before assuming `{=expr}`).
  Wrap inline `<script>` and `<style>` bodies in `{| ... |}`.
- The brand is the five-colour system in `main.css` (ink, star, sightline, paper, muted) and
  the Southern Cross mark. Do not introduce colours outside it.
- Writing style: plain Australian English, no em or en dashes, no marketing filler, no
  exclamation marks, no emoji. The elf hands you the full list as STYLE.md when it asks for
  work.
- Verify before you finish: `QUARKUS_HTTP_PORT=8765 QUARKUS_ROQ_GENERATOR_BATCH=true mvn -q -B package quarkus:run`
  must succeed and `target/roq/index.html` must exist.
- There is no blog or news collection on this site. A request for a "post" means adding a
  section to the single page unless the owner asks for a news section to be created.
