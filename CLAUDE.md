# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository contains the LaTeX source for a professional resume, compiled with XeLaTeX. The compiled `resume.pdf` is committed to the repo and triggers an automatic website redeploy via GitHub Actions when pushed to `main`.

## Building

```bash
make
```

Or directly:

```bash
xelatex resume.tex
```

### Prerequisites

- XeLaTeX — on macOS: `brew install --cask mactex`
- TeX Gyre fonts — `sudo tlmgr install tex-gyre`

## File Structure

- `resume.tex` — the single source file for the entire resume
- `resume.pdf` — compiled output; **must be committed** so the GitHub Action can detect changes and trigger the website redeploy
- `Makefile` — compiles `resume.pdf` from `resume.tex` using `xelatex`
- `.github/workflows/notify-website.yml` — triggers a Vercel deploy hook when `resume.pdf` changes on `main`

## CI/CD Behavior

Pushing a new `resume.pdf` to `main` automatically triggers a Vercel redeploy of the personal website via a deploy hook stored in the `VERCEL_DEPLOY_HOOK_URL` secret. This means the PDF must be rebuilt and committed locally before pushing.

## Styling

Colors are defined near the top of `resume.tex`:

| Name | Hex | Usage |
|---|---|---|
| `text1` | `#2b2b2b` | Body text |
| `headings` | `#701112` | Section headings |
| `linkcolor` | `#506266` | Hyperlinks |

Fonts: TeX Gyre Termes (serif, body) via `\setmainfont`.
