# The Prompt Brief

An internal training tool for **Microsoft 365 Copilot prompting**, built for COEO Solutions as part of the **COEO AI Enablement** program.

It teaches a single, repeatable habit — the four-block framework (**Goal · Context · Expectations · Source**) — and gives staff ready-to-use prompts, an interactive prompt builder, and official video tutorials, all in one page.

**Current version:** 1.7.0 (see [CHANGELOG.md](./CHANGELOG.md))

---

## What's in it

The tool is organized into four tabs:

1. **Basic Prompting** — the four-block framework, a "Vague in, clear out" before/after with a per-department selector, a Library of ready-to-use prompts by app (Copilot Chat, Outlook, Word, Excel, PowerPoint, Teams), and a Common Mistakes section.
2. **Advanced Prompting** — seven techniques adapted from Microsoft's own prompting guidance and Azure AI Foundry docs, each with an editable snippet that can be folded into the builder.
3. **Video Tutorials** — Microsoft's featured prompting video, per-app demo links, a live-training callout, and an internal Vimeo video library with a tab selector.
4. **Build a prompt** — an interactive builder that assembles a four-block prompt live, with a product picker, tone/format chips, department starting points, and inline advanced techniques.

---

## Technical overview

- **Single file.** Everything (HTML, CSS, JS) lives in `prompting-tool.html`. No build step, no framework, no external runtime dependencies.
- **External resources.** Only Google Fonts, the Vimeo player script (`player.vimeo.com/api/player.js`), and the COEO banner (embedded inline as base64) are loaded.
- **Vanilla JS.** All interactivity is plain JavaScript in one `<script>` block at the bottom of the file.
- **Clipboard.** Copy actions use the async Clipboard API with a sandbox-safe `execCommand` fallback, so they work inside a Confluence iframe.

---

## Deployment

### GitHub Pages
1. Commit `prompting-tool.html` to the repository.
2. Enable GitHub Pages (Settings → Pages) pointing at the branch/folder that contains the file.
3. The tool is served at `https://<org>.github.io/<repo>/prompting-tool.html`.

### Confluence (embed)
Embed the GitHub Pages URL in a Confluence page using an **iframe / HTML macro**:

```html
<iframe src="https://<org>.github.io/<repo>/prompting-tool.html"
        style="width:100%;height:1400px;border:0"></iframe>
```

Notes:
- The tool is designed to work inside a sandboxed iframe (custom modals instead of `window.confirm`, clipboard fallback, no `localStorage`).
- The internal Vimeo videos are an iframe inside the Confluence iframe; playback works, but fullscreen depends on the outer Confluence iframe allowing it.

---

## Updating content

Most content lives in plain JavaScript arrays/objects near the bottom of `prompting-tool.html`. No markup editing needed to add examples.

| What you want to change | Where to edit | Shape |
|---|---|---|
| Library prompts (by app) | `const library = { ... }` | `{ t, g, c, e, s }` per item (title, goal, context, expectations, source) |
| "By department" builder samples | `const departments = [ ... ]` | `{ key, name, ic, items:[{ t, g, c, e, s }] }` |
| "Vague in, clear out" examples | `const baExamples = [ ... ]` | `{ key, name, before, after:[{c, t}] }` |
| Advanced technique snippets | `const techniques = [ ... ]` | `{ key, name, ic, desc, snippet }` |
| Internal Vimeo videos | `const vimeoVideos = [ ... ]` | `{ id, title, ratio }` (ratio = padding %) |

**Adding a Vimeo video** (example):

```js
const vimeoVideos = [
  { id:"1207915789", title:"Copilot for Operations", ratio:53.94 },
  { id:"1208213927", title:"Copilot for IT",         ratio:56.28 }
];
```

Grab the `id` and the `padding` percentage from the embed code Vimeo gives you (`Share → Embed`).

---

## Versioning

This project uses [Semantic Versioning](https://semver.org/) (MAJOR.MINOR.PATCH).

**On every change, do all three:**
1. Bump the version in the **HTML header comment** (top of `prompting-tool.html`).
2. Bump the visible **footer version tag** (`.footer-ver`).
3. Add an entry to **[CHANGELOG.md](./CHANGELOG.md)**.

The CHANGELOG entries are written to double as Git commit/PR notes.

---

## Credits

- **Created by** Ron Mangune — [linkedin.com/in/ronmangune](https://www.linkedin.com/in/ronmangune/)
- Built for **COEO Solutions**, part of the **COEO AI Enablement** program.
- Prompting guidance adapted from Microsoft's official Copilot documentation and Azure AI Foundry prompt-engineering docs.
