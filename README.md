# Dale Rogers Portfolio — Simplified Astro Build

## Status Badges

<!-- Badges will appear here after CI/CD is set up -->

---

## Project TODO

See [TODO.md](./TODO.md) for a checklist of GitHub and CI/CD best practices, and ongoing project tasks.

---

This is a minimal, content-first personal portfolio built with [Astro](https://astro.build), using a clear directory structure and minimal dependencies. It prioritises simplicity, hardcoded content, and extensibility over framework abstraction.

---

## 🚧 Getting Started

```sh
npm install
npm run dev
````

Local site will be available at [http://localhost:4321](http://localhost:4321)

---

## 📁 Project Structure

```
dale-rogers-portfolio-simplified/
├── public/                # Static assets (icons, images, etc.)
├── src/
│   ├── pages/             # Astro pages (routed automatically)
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── contact.astro
│   │   └── ...
│   ├── components/        # Reusable UI components
│   ├── styles/            # Global and layer-based styles
│   └── data/              # Site metadata, if needed
├── tailwind.config.ts     # Optional Tailwind configuration
├── astro.config.mjs       # Astro project config
├── package.json
└── README.md
```

---

## 📦 Commands

| Command           | Description                          |
| ----------------- | ------------------------------------ |
| `npm install`     | Install dependencies                 |
| `npm run dev`     | Start local dev server               |
| `npm run build`   | Build the site for production        |
| `npm run preview` | Preview built site before deployment |

---

## 🎯 Project Principles

* **Minimal by default** – No unnecessary libraries or abstractions.
* **Hardcoded when simpler** – Use `.astro` files directly unless logic justifies abstraction.
* **Extensible when needed** – Structure supports future growth without rewrites.
* **Content-first** – Prioritise writing and layout over interactivity or automation.

---

## 📚 Learn More

* [Astro Documentation](https://docs.astro.build)
* [Cursor Rules (internal)](./.cursor/rules/) — development guidelines and project rules

---

## ⚠️ Astro CSS Import Limitation

Astro does **not** support importing CSS files directly in the frontmatter (the `--- ... ---` block) of `.astro` files. To include global styles, always use a `<link rel="stylesheet" href="/styles/global.css" />` tag in your `<head>`, or import CSS in your main entry points (e.g., `src/pages/_app.astro` if using one).

**Incorrect:**
```js
---
import '../styles/global.css'; // ❌ This will cause a build error
---
```

**Correct:**
```html
<head>
  ...
  <link rel="stylesheet" href="/styles/global.css" />
</head>
```

This project follows this convention for all global and shared styles.

---

## 🎨 Theming & Layout Consistency

All layout files (`src/layouts/*.astro`) now use a shared `site-body` class on the `<body>` tag. This class is defined in `src/styles/global.css` and sets the background and text colour to match the brand palette:

```css
.site-body {
  background: #F2F2F2;
  color: #262626;
}
```

This replaces previous inline body styles (e.g., `bg-white`, `text-neutral-900`) and ensures consistent theming across all pages. To update the site’s look, simply adjust the `.site-body` class in your global CSS.

---

## 🆕 Recent Updates

- **Hero Section Polish:**
  - Concise heading and improved CTA.
  - Hero button now supports an inline icon (see Button.astro usage below).
  - Animated, morphing avatar blob with pulsing rainbow gradient and slow rotation.
- **Icon Usage:**
  - Uses [Heroicons](https://heroicons.com/) SVGs inline via a named slot in Button.astro.
  - Example usage:
    ```astro
    <Button label="Get in touch">
      <svg slot="icon" ...>...</svg>
    </Button>
    ```
  - See `src/components/ui/Button.astro` for details.
- **About/Header/Styles:**
  - About and Header sections updated for layout and style consistency.
  - New and updated utility classes in `src/styles/global.css`.

---
