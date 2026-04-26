# Artifacts

A collection of single-page interactive tools and calculators, hosted on GitHub Pages.

**Live site:** https://artifacts.curiousstranger.org/

## Tools

| Tool | Description |
|------|-------------|
| [Housing Affordability Calculator](housing-calculator.html) | Estimate what you can afford to rent or buy based on income, DTI, and the 30% rule |

## Structure

Each tool is a single self-contained `.html` file — no build step, no dependencies to install. CDN-loaded libraries (React, Tailwind) are referenced directly in each file. `index.html` serves as the landing page and links to all tools.

## Adding a new tool

1. Create a new `.html` file (e.g. `my-tool.html`) in the repo root.
2. Add a card for it in `index.html` following the existing pattern.
3. Push to `main` — GitHub Pages deploys automatically.

## Stack

- React 18 (UMD via CDN) + Babel standalone for JSX
- Tailwind CSS (CDN)
- No framework, no bundler, no build process
