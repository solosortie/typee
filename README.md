# Typee

A single-page Markdown editor. Paper-textured, distraction-free, and fully local — nothing you write ever leaves your browser.

**[Live demo →](https://typee.pacify.site)**

![Typee preview](assets/og-image.png)

## What it is

Typee is one full-page canvas for writing Markdown, with a small draggable tab in the corner holding everything else. No sidebar, no dashboard, no sign-up, no account, no server.

- **Split** — write raw Markdown on the left, see it rendered live on the right
- **Flow** — a single pane where your Markdown syntax resolves inline as you type (bold, italic, headings, quotes — WYSIWYG-style, syntax marks stay dimly visible so nothing feels hidden)
- **Write** — full-width raw editor, no distractions
- **Read** — full-width rendered preview
- **Night page** — a warm, ink-on-dark theme toggled with a small icon button in the tab's corner, not a stark black inversion, and without the paper grain (grain is a light-mode-only effect)
- **Export** — download as `.md` or a self-contained styled `.html` file, or copy the rendered text
- Everything autosaves to `localStorage` as you type

## Why it looks the way it does

The design brief was "paper, not dashboard." Warm cream background, a subtle grain texture, a serif body face (Source Serif 4) for the writing surface, and a humanist sans (Inter) reserved only for the small UI chrome in the tab. The floating tab itself is treated like a physical sticky note — slightly tilted, real drag physics, its own soft shadow.

## Running it

It's a single HTML file. Open `index.html` directly in any modern browser, or serve the folder:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

No build step, no dependencies, no `npm install`. The only external requests are two Google Fonts (Source Serif 4, Inter) — everything else, including the Markdown engine, runs entirely client-side with zero libraries.

## Project structure

```
typee/
├── index.html              # the whole app — markup, styles, and logic
├── assets/
│   ├── favicon.svg          # the T mark, primary favicon
│   ├── favicon.ico          # multi-size (16/32/48px) fallback icon
│   ├── favicon-16.png
│   ├── favicon-32.png
│   ├── favicon-48.png
│   ├── apple-touch-icon.png
│   ├── og-image.svg
│   └── og-image.png         # social share preview image
├── LICENSE
└── README.md
```

## Markdown support

Typee ships a small hand-written Markdown renderer (no `marked`/`markdown-it`/etc — kept dependency-free on purpose):

- Headings (`#`, `##`, `###`)
- Bold, italic, bold+italic, strikethrough
- Inline code and fenced code blocks
- Blockquotes
- Ordered and unordered lists
- Links and images
- Horizontal rules

## License

MIT — see [LICENSE](LICENSE).

