# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-page static web app that generates standardized email signatures for **Sanatorio Allende**. A user fills out a form (name, title, area, position, extension, cell) and the app renders an HTML signature preview and produces a downloadable PNG of it. The UI is in Spanish.

There is no build step, package manager, backend, or test suite. Everything lives in `index.html` (markup + CSS + JS inline). Open it in a browser to run it; it must be served from a location where the sibling image assets (`Logo para firmas de mailing.png`, `fondo.jpg`) resolve.

## Architecture

`index.html` is the entire application. It has three coupled parts:

1. **Form** — Bootstrap 5 (CDN) form with per-field `maxlength` limits. Fields and their limits are duplicated in two places that must stay in sync: the HTML `maxlength` attributes and the `campos` array in the JS (`{ id, max }`). The character-count limits are deliberate — they keep the generated signature from overflowing its fixed 505px width.

2. **Live character counters** — `updateCounter`/`updateInputStyle` show remaining characters and apply `warning` (≥70%) / `danger` (≥90%) styles. The name field's limit is dynamic: `actualizarMaxNombre` shrinks it from 27 to 24 when a title (`titulo`) is selected, since the title prefix eats into the same visual line.

3. **Signature generation** — the form `submit` handler builds `firmaHtml` as a template literal with fully inline styles (required for email-client compatibility), injects it into `#firma`, then rasterizes it with **html2canvas** (CDN) into a downloadable PNG. The signature layout is a fixed 505px two-column design (logo left, details right) with hardcoded brand color `#367fc2` and a fixed phone number `0810 555 2553`.

## Editing conventions

- **Signature styles must be inline.** Email clients strip `<style>` blocks, so all styling inside `firmaHtml` uses `style="..."` attributes. Do not refactor these into CSS classes.
- **When adding/changing a field limit**, update both the HTML `maxlength` and the `campos` array (and if it affects the name line, `actualizarMaxNombre`).
- **Spanish accents** are written as HTML entities in the signature (`informaci&oacute;n`) to survive encoding across mail clients — several past commits were accent fixes. Keep this pattern for text baked into the signature.
- The signature image references `Logo para firmas de mailing.png` by relative path; if the logo changes, update that reference. `logo.jpg`, `logo.png`, `logo-viejo.jpg` are unused historical assets.

## Repo notes

- `index.old.html` is a previous version kept for reference; the live file is `index.html`.
- Deployment is manual: commits are pushed to `origin` (GitHub: Santolei/Firma) and the static files are served from wherever they are hosted. There is no CI/CD.
