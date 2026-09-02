# Hayden & Osborn at 3 PM — viewing brief

One static page, no build step. `index.html` is the whole site: every photo is
embedded as a data URI (from the Zillow listing pages for zpid 72291807 and
72291763), so nothing loads from a third-party host and there is nothing to
bundle.

Vercel serves this with zero configuration — a repository whose root holds an
`index.html` is a static site, and `vercel.json` here only sets clean URLs and a
cache header. It deliberately does **not** use the legacy `builds` key: that
switches zero-config off and ships only the files it names, which is what left
this project serving a placeholder instead of the brief.
