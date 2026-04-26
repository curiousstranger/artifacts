# Agent Instructions

This repo is a flat collection of self-contained HTML SPAs deployed to GitHub Pages. No build system, no package manager, no server.

## Key conventions

- Each tool is a single `.html` file in the repo root.
- All dependencies (React, Tailwind, etc.) are loaded from CDN — do not add `package.json` or a bundler.
- `index.html` is the landing page. When adding a new tool, always add a card there too.
- Keep each file fully self-contained: styles, logic, and markup in one file.

## Adding a new tool

1. Create `<tool-name>.html` in the repo root.
2. Use this shell as a starting point — it matches the existing stack:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tool Name</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.2/babel.min.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-slate-50">
  <div id="root"></div>
  <script type="text/babel">
    const { useState } = React;

    function App() {
      return <div>Hello</div>;
    }

    ReactDOM.createRoot(document.getElementById("root")).render(<App />);
  </script>
</body>
</html>
```

3. Add a card to `index.html` inside `.artifact-list`:

```html
<a href="<tool-name>.html" class="artifact-card">
  <div class="artifact-info">
    <h2>Tool Name</h2>
    <p>One-sentence description.</p>
  </div>
  <span class="arrow">→</span>
</a>
```

4. Update the tools table in `README.md`.

## What not to do

- Do not introduce a build step, bundler, or `node_modules`.
- Do not create subdirectories for individual tools.
- Do not use `import`/`export` ES module syntax — CDN UMD builds don't support it.
- Do not add backend code or server-side logic.
