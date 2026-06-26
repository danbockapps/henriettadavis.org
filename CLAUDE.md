# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static personal/campaign website for Henrietta Davis. There is no build
step, framework, or backend — the entire site is hand-written HTML styled
with Bootstrap (loaded from a CDN). The repository is deployed to a VPS by
pulling it with git and serving the `public/` directory with nginx.

## Structure

- **public/**: The web root served by nginx.
  - `index.html`: The entire site — content plus a small inline `<style>`
    block. Bootstrap 3 CSS/JS and jQuery are loaded from CDNs.
  - `404.html`: Not-found page.
  - `favicon.ico`, `cover.jpg`, `family.png`, `henriettadavis.jpg`,
    `paris.jpg`, `together.jpg`: Static assets referenced by `index.html`.
- `firebase.json`, `firestore.*`, `.firebaserc`: Leftover from the previous
  Firebase deployment; unused now and safe to remove.

## Editing

Edit `public/index.html` directly. There is nothing to compile or bundle —
opening the file in a browser shows exactly what gets served.

## Deployment

The site is hosted on a VPS running nginx. To deploy, `git pull` on the
server; nginx serves the `public/` directory directly. No build is run.
