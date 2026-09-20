# Attribution and distribution notes

## Upstream

Repository: https://github.com/YusufCeng1z/svelte-gsap-template

Commit: `a6648f678e3c8a592f108543771298d42ded7f66`

Author: Yusuf Cengiz (`YusufCeng1z`)

The upstream README declares:

> Engineered by [YusufCeng1z](https://github.com/YusufCeng1z).
> Released and open-sourced under the MIT License.

The upstream repository did not contain a standalone license file at the pinned commit.
The distributor added `LICENSE` with the standard MIT text and the supported copyright line `Copyright (c) 2026 Yusuf Cengiz`, based on the upstream README declaration.

## GSAP dependency

GSAP remains an npm dependency and is not vendored in this package.
GSAP 3.15.0 uses the GreenSock Standard License published at https://gsap.com/community/standard-license/.
This package is a website template and does not provide a visual animation builder, no-code animation editor, or competing hosted animation service.
Additional dependency notices are recorded in `THIRD_PARTY_NOTICES.md`.

## Asset review

The upstream `aura-preview.png`, `static/og-image.png`, and `static/ascii-art.gif` were removed because their provenance was not documented separately.
The upstream Svelte favicon and the original Logoipsum-style wordmark were replaced with original, simple SVG marks authored for this distribution.
The package includes no remote fonts or remote media.

## Functional changes

External contact and social links, the inactive newsletter input, production SEO URLs, personal author links in the rendered site, third-party brand names, and named testimonials were removed or replaced with neutral local content.
The original author link remains only in factual attribution and license documentation.
The hero now uses a local CSS background instead of an undocumented raster animation.
The package uses `@sveltejs/adapter-static` with a fallback page and needs no environment variables.
