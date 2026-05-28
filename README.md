# Kotodama (琴玉)

[![Hugo Version](https://img.shields.io/badge/Hugo-0.100.0+-blue)](https://gohugo.io/)
[![License](https://img.shields.io/badge/License-CC--BY--4.0-brightgreen)](LICENSE)
[![GitHub Release](https://img.shields.io/github/v/release/carmelolg/kotodama)](https://github.com/carmelolg/kotodama/releases)
[![GitHub Stars](https://img.shields.io/github/stars/carmelolg/kotodama?style=social)](https://github.com/carmelolg/kotodama)

A minimal, literary Hugo theme for poets and writers. **Kotodama** (琴玉, "word spirit") is designed for sharing poetry and essays with intention, clarity, and beauty.

**[🎨 Live Demo](https://carmelolg.github.io/kotodama/)**

---

## ✨ What is Kotodama?

Kotodama is a theme built for **poets, writers, and essayists** who want to share their work with a distraction-free, elegant interface. It separates poetry from essays, includes full-text search, supports multiple languages, and adapts beautifully to dark mode.

**No ads. No clutter. Just words.**

---

## 🎯 Features

- ✅ **Separate collections** — Poetry and essays in distinct sections
- ✅ **Full-text search** — Find poems and essays instantly
- ✅ **Dark mode** — Auto-detect via `prefers-color-scheme` + manual toggle
- ✅ **Responsive design** — Mobile-first, works on all devices
- ✅ **Elegant typography** — Optimized for reading
- ✅ **RSS feed** — Syndicate your work
- ✅ **i18n support** — English and Italian built-in
- ✅ **Featured content** — Highlight best poems and essays on home page
- ✅ **Minimal JavaScript** — Fast, accessible, lightweight
- ✅ **WCAG 2.1 AA compliant** — Accessible to all readers
- ✅ **Configurable** — Toggle tags, customize colors, set metadata

---

## 🚀 Quick Start (5 minutes)

### 1. Install the theme

```bash
git submodule add https://github.com/carmelolg/kotodama themes/kotodama
```

### 2. Create your config

Copy this to `hugo.toml`:

```toml
baseURL  = "https://yourusername.github.io/kotodama/"
title    = "Il mio quaderno"
theme    = "kotodama"
languageCode = "it"

[params]
  author = "Il tuo nome"
  description = "Poesie e scritti da condividere con lentezza."
  tagline = "Ogni parola ha un peso."
  authorBio = "Poeta e scrittore."
  email = "hello@example.org"
  website = "https://example.org"
  socialLinks = [
    { name = "GitHub", url = "https://github.com/yourusername" },
    { name = "Twitter", url = "https://twitter.com/yourusername" }
  ]
  showTags = false

[menu]
  [[menu.main]]
    name = "Poesie"
    url = "/poems/"
    weight = 1
  [[menu.main]]
    name = "Scritti"
    url = "/essays/"
    weight = 2
  [[menu.main]]
    name = "Ricerca"
    url = "/search/"
    weight = 3
```

### 3. Create your first poem

```bash
hugo new poems/my-first-poem.md
```

Edit `content/poems/my-first-poem.md`:

```yaml
---
title: "Il mio primo verso"
date: 2024-05-28
draft: false
---

# Verso

La tua poesia inizia qui.
Una riga per volta,
una pausa tra le parole.
```

### 4. Create your first essay

```bash
hugo new essays/my-first-essay.md
```

Edit `content/essays/my-first-essay.md`:

```yaml
---
title: "Riflessioni sulla scrittura"
date: 2024-05-28
draft: false
---

# Sul significato delle parole

La scrittura è...
```

### 5. Preview locally

```bash
hugo server
```

Visit `http://localhost:1313/` 🎉

---

## 📚 Complete User Guide

### Content Structure

Your site should have this folder structure:

```
content/
├── _index.md           ← Home page intro (optional)
├── poems/
│   ├── _index.md       ← Poems listing page (required)
│   ├── poem-one.md
│   └── poem-two.md
├── essays/
│   ├── _index.md       ← Essays listing page (required)
│   ├── essay-one.md
│   └── essay-two.md
└── search.md           ← Search page (required, layout: search)
```

### Home Page

Create `content/_index.md` (optional):

```yaml
---
---

# Quaderno di luce

Poesie e scritti da condividere con lentezza.
```

### Poetry Collection

Create `content/poems/_index.md`:

```yaml
---
title: "Poesie"
---
```

Create poems in `content/poems/` with this front matter:

```yaml
---
title: "Titolo della poesia"
date: 2024-05-28
draft: false
---

# Your poem content

Line by line
word by word
silence between.
```

### Essays Collection

Create `content/essays/_index.md`:

```yaml
---
title: "Scritti"
---
```

Create essays in `content/essays/` with this front matter:

```yaml
---
title: "Titolo dello scritto"
date: 2024-05-28
draft: false
---

# Your essay content

Paragraph after paragraph,
thought after thought.
```

### Search Page

Create `content/search.md`:

```yaml
---
title: "Ricerca"
layout: "search"
---
```

This creates a full-text search interface.

---

## ⚙️ Configuration Guide

### Required Settings

```toml
baseURL = "https://yourusername.github.io/kotodama/"
title = "Il mio quaderno"
theme = "kotodama"

[params]
  author = "Il tuo nome"
  description = "Una breve descrizione"
  tagline = "Il tuo tagline"
```

### Optional Settings

```toml
[params]
  authorBio = "Chi sei e cosa scrivi"
  email = "you@example.org"
  website = "https://yoursite.org"
  
  # Social links
  socialLinks = [
    { name = "GitHub", url = "https://github.com/username" },
    { name = "Twitter", url = "https://twitter.com/username" },
    { name = "Instagram", url = "https://instagram.com/username" }
  ]
  
  # Appearance
  dateFormat = "02 Jan 2006"
  showTags = false  # Hide tags in article listings
  
  # Featured content
  featuredPoemsCount = 1
  featuredEssaysCount = 1
```

### Enabling Italian Language

To use Italian as default language:

```toml
languageCode = "it"

[languages]
  [languages.it]
    label = "Italiano"
    locale = "it-IT"
  [languages.en]
    label = "English"
    locale = "en-US"
```

---

## 🎨 Customizing Colors

Edit `assets/css/main.css` to customize the theme colors:

```css
:root {
  /* Light mode */
  --bg: #fafaf8;           /* Background */
  --paper: #ffffff;        /* Card background */
  --ink: #2a2a2a;          /* Text color */
  --soft: #6a665f;         /* Muted text */
  --accent: #7d4b39;       /* Links and accents */
  --line: #e0dcd7;         /* Borders */
}

@media (prefers-color-scheme: dark) {
  :root {
    --bg: #1a1a1a;
    --paper: #2a2a2a;
    --ink: #e8e6e1;
    --soft: #bab3a8;
    --accent: #d4a79f;
    --line: #3a3a3a;
  }
}
```

Save and rebuild: `hugo` — your changes will apply instantly.

---

## 🔍 Full-Text Search

The search page provides real-time search across all poems and essays:

- **Type to search** — Results appear instantly
- **Smart ranking** — Title matches appear first
- **Search highlighting** — Matching terms highlighted in results
- **No results fallback** — Links to browse all poems/essays
- **Accessible** — Keyboard navigation and screen reader support

### How It Works

Hugo builds a JSON search index at build time. The search page (`search.md`) includes JavaScript that:
1. Loads the search index
2. Filters poems and essays in real-time
3. Sorts by title relevance
4. Highlights matching text
5. Shows result count

---

## 🌍 Language Support

The theme comes with **Italian** and **English** built-in. Switch languages in `hugo.toml`:

```toml
languageCode = "it"  # Italian
# OR
languageCode = "en"  # English
```

### Creating a New Language

1. Copy `i18n/en.toml` → `i18n/[lang-code].toml`
2. Translate all values
3. Set `languageCode = "[lang-code]"` in your config

---

## 🌓 Dark Mode

Dark mode is **automatic** but can be overridden by the user with the theme toggle button in the header.

- Respects system preference (`prefers-color-scheme`)
- User can manually switch themes
- Preference saved in `localStorage`
- All pages fully styled for both modes

---

## 📱 Mobile & Responsive

The theme is **mobile-first**:

- Works on all screen sizes (320px and up)
- Touch-friendly button sizes (44px minimum)
- Readable typography at all scales
- Optimized performance on slow connections

---

## ♿ Accessibility

Kotodama is built to **WCAG 2.1 AA** standards:

- ✅ Color contrast ≥ 4.5:1 for readability
- ✅ Focus indicators on all interactive elements
- ✅ Keyboard navigation throughout
- ✅ Semantic HTML and ARIA labels
- ✅ Screen reader friendly
- ✅ Accessible search with `aria-live` regions

---

## 📄 License

[CC-BY-4.0](LICENSE) (Creative Commons Attribution 4.0)

© 2024 carmelolg

This work requires attribution in any redistribution or use.

---

## 🤝 Contributing

Found a bug? Have an idea? [Open an issue](https://github.com/carmelolg/kotodama/issues) or [submit a pull request](https://github.com/carmelolg/kotodama/pulls).

---

## 🎓 Learn More

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Markdown Guide](https://www.markdownguide.org/)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)

---

**Happy writing.** 📝
