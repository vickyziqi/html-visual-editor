<div align="center">

# ✦ HTMLEdit

### Edit AI-Generated HTML Like a PowerPoint

**Paste HTML → Click to edit → Add animations → Copy code**

No coding. No re-prompting. No friction.

[🇺🇸 Open English Editor](https://zhizhiqiu.github.io/html-visual-editor/index-en.html) · [🇨🇳 打开中文编辑器](https://zhizhiqiu.github.io/html-visual-editor/index-zh.html) · [⭐ Star on GitHub](https://github.com/zhizhiqiu/html-visual-editor)

</div>

---

## The Problem

AI tools (ChatGPT, Claude, Gemini) generate beautiful HTML slides and landing pages in seconds.

But the moment you want to **change a word, tweak a font, or add an animation**, you have to:
- Go back to the AI and re-prompt (lose your edits)
- Open a code editor (requires coding knowledge)
- Accept imperfect output

**HTMLEdit fills that gap.** It's the last mile of AI-generated HTML.

---

## Demo

> Paste → Click → Edit → Done.

```
📋  Paste AI-generated HTML
     ↓
✏️  Click any text → type directly
     ↓
🎨  Select text → floating toolbar (bold / italic / size / color)
     ↓
✨  Click any element → add animation (fade / rise / float / pulse / shake)
     ↓
📤  "Copy Code" → clean HTML with all edits baked in
```

---

## Features

| Feature | Details |
|---------|---------|
| **Click-to-Edit** | Click any text element (h1–h6, p, li, td, button…) and type directly |
| **Floating Toolbar** | Select text → bold, italic, underline, font size, color picker, alignment |
| **Animation Presets** | 6 one-click animations: Fade In · Rise Up · Float · Pulse · Shake · Remove |
| **Animation Controls** | Speed, duration, delay, loop sliders — fine-tune without code |
| **Open HTML Files** | Open .html files directly from your computer |
| **Clean Export** | One-click copy → clean HTML with edits + animations, tool code stripped |
| **Sandboxed Preview** | User HTML in sandboxed iframe — no access to your data |
| **Zero Dependencies** | Single .html file. No npm, no server, no build step |
| **Bilingual** | Full UI in English and Chinese |

---

## Quick Start

**Option 1 — Use online (GitHub Pages):**
- [English version](https://zhizhiqiu.github.io/html-visual-editor/index-en.html)
- [中文版本](https://zhizhiqiu.github.io/html-visual-editor/index-zh.html)

**Option 2 — Download and run locally:**
```bash
# Clone the repo
git clone https://github.com/zhizhiqiu/html-visual-editor.git

# Open the editor (no server needed)
open html-visual-editor/index-en.html
```

**Option 3 — Just download one file:**

Download [`index-en.html`](index-en.html) or [`index-zh.html`](index-zh.html) — it's a single self-contained file. Open it in any browser. Done.

---

## How It Works (Technical)

HTMLEdit uses a clever architecture to enable safe, sandboxed editing:

1. User HTML is rendered in a `sandbox="allow-scripts"` iframe (no `allow-same-origin` — safe)
2. A script is injected that marks text elements as `contenteditable` and listens for clicks
3. All communication between the editor UI and the iframe uses `window.postMessage`
4. The floating toolbar and animation panel live in the main window, positioned over the iframe
5. Export: a `getHTML` postMessage triggers the iframe to strip editing markup and return clean HTML

The sandboxed iframe means the user's HTML code **cannot access your cookies, localStorage, or filesystem** — even if it contains malicious scripts.

---

## Animation System

HTMLEdit adds 5 named keyframe animations with the `__he_` namespace:

```css
@keyframes __he_fadeIn  { from{opacity:0} to{opacity:1} }
@keyframes __he_slideUp { from{opacity:0;transform:translateY(22px)} to{opacity:1;transform:translateY(0)} }
@keyframes __he_float   { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-10px)} }
@keyframes __he_pulse   { 0%,100%{transform:scale(1)} 50%{transform:scale(1.06)} }
@keyframes __he_shake   { 0%,100%{transform:translateX(0)} 25%{transform:translateX(-6px)} 75%{transform:translateX(6px)} }
```

These are injected alongside the user HTML, so they're preserved in the exported code.

---

## Who Is This For

- **Vibe coders** who use AI to generate HTML presentations and want to tweak the content
- **Designers** who receive AI-generated mockups and need to adjust text quickly
- **Non-technical founders** building landing pages with AI who want fine-grained control
- **Anyone** who has ever thought "I just want to change this one word without asking the AI again"

---

## Files

```
html-visual-editor/
├── index.html      # Landing page
├── index-en.html   # English editor (single file, zero dependencies)
├── index-zh.html   # Chinese editor (单文件，零依赖)
└── README.md
```

---

## Design

Built with a **Morandi color palette** — muted, warm, desaturated tones that feel calm and focused. The goal is an editor that doesn't feel like a developer tool, but like a creative tool.

---

## Contributing

Issues and PRs welcome. The core is intentionally a single HTML file — keep it that way.

When adding features, the constraints are:
- No external dependencies (no npm packages, no CDN scripts beyond Google Fonts)
- Single-file distribution must work
- The sandboxed iframe model must be preserved (no `allow-same-origin`)

---

## License

MIT — do whatever you want with it.

---

<div align="center">

Made for the vibe coding era · ⭐ Star if this saved you time

</div>
