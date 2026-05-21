# azwatercheck.com → aquafeelsolutionsarizona.com redirect

This repo serves a domain redirect for the legacy `azwatercheck.com` domain.

After the brand rebranded from AZ Water Check to Aquafeel Solutions Arizona on 2026-05-21,
this lightweight GitHub Pages repo handles redirects for any traffic still hitting the old domain.

**Redirect strategy:**
- `index.html` with `<meta http-equiv="refresh">`, canonical link, and JS `window.location.replace` (preserves path + query)
- `404.html` clones the same behavior so deep paths (`/service-areas/phoenix/`, etc.) also redirect to their counterpart on the new domain

**Why not a true HTTP 301?**
GitHub Pages doesn't support server-side 301s. For a true 301, put Cloudflare in front of the domain and use a Page Rule. Until then, the meta-refresh + canonical combo is treated by Google as a "soft 301" — combined with a Search Console Change of Address signal, ranking transfer happens cleanly.

**Email (MX records) is unaffected** — Web/HTTP routing only.
