# Kotodama (琴玉)

[![Hugo Version](https://img.shields.io/badge/Hugo-0.100.0+-blue)](https://gohugo.io/)
[![License](https://img.shields.io/badge/License-CC--BY--4.0-brightgreen)](LICENSE.md)
[![GitHub Release](https://img.shields.io/github/v/release/carmelolg/kotodama)](https://github.com/carmelolg/kotodama/releases)
[![GitHub Stars](https://img.shields.io/github/stars/carmelolg/kotodama?style=social)](https://github.com/carmelolg/kotodama)

Kotodama is a minimal Hugo theme for poets and writers. It separates poetry from essays, supports search, dark mode, multilingual sites, and optional Google Analytics with GDPR consent.

**[Live demo](https://carmelolg.github.io/kotodama/)**

---

## What this theme gives you

- Separate content collections for poems and essays
- Home page with featured content
- Full-text search
- Dark mode with manual toggle
- i18n support
- Responsive, typography-focused layout
- Optional Google Analytics with cookie consent banner

---

## Quick start

Use this if you want the theme up and running fast.

### 1. Add the theme

```bash
git submodule add https://github.com/carmelolg/kotodama themes/kotodama
```

### 2. Create a minimal `hugo.toml`

```toml
baseURL = "https://example.org/"
title = "Kotodama"
theme = "kotodama"
defaultContentLanguage = "it"

[outputs]
  home = ["HTML", "JSON"]

[taxonomies]
  tag = "tags"

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

[params]
  description = "Poesie e scritti da condividere con lentezza."
  tagline = "Ogni parola ha un peso."
  author = "Nome Autore"
  authorBio = "Poeta e scrittore."
  email = "hello@example.org"
  website = "https://example.org"
  socialLinks = [
    { name = "GitHub", url = "https://github.com/username" }
  ]
  dateFormat = "02 Jan 2006"
  showTags = false
  favicon = ""
  footerNote = ""
  googleAnalyticsID = ""

[services]
  [services.googleAnalytics]
    ID = ""
```

### 3. Create the required content files

```bash
mkdir -p content/poems content/essays content/search
touch content/_index.md content/poems/_index.md content/essays/_index.md content/search/index.md
```

Example files:

```yaml
# content/_index.md
---
---

Benvenuto in questo spazio di parole.
```

```yaml
# content/poems/_index.md
---
title: "Poesie"
---
```

```yaml
# content/essays/_index.md
---
title: "Scritti"
---
```

```yaml
# content/search/index.md
---
title: "Ricerca"
layout: "search"
---
```

### 4. Add your first content

```bash
hugo new poems/my-first-poem.md
hugo new essays/my-first-essay.md
```

Poem example:

```yaml
---
title: "Il mio primo verso"
date: 2024-05-28
draft: false
---

La tua poesia inizia qui.
```

Essay example:

```yaml
---
title: "Riflessioni sulla scrittura"
date: 2024-05-28
draft: false
---

La scrittura è...
```

### 5. Run locally

```bash
hugo server
```

---

## Content structure

Recommended layout:

```
content/
├── _index.md
├── poems/
│   ├── _index.md
│   ├── poem-one.md
│   └── poem-two.md
├── essays/
│   ├── _index.md
│   ├── essay-one.md
│   └── essay-two.md
└── search/
    └── index.md
```

Each poem/essay page should use standard front matter:

```yaml
---
title: "Title"
date: 2024-05-28
draft: false
---
```

---

## Configuration reference

### Hugo site settings

These are the key Hugo settings used by the theme:

| Setting | Required | Notes |
| --- | --- | --- |
| `baseURL` | Yes | Canonical site URL |
| `title` | Yes | Site name shown in the header and browser title |
| `theme` | Yes | Must be `kotodama` |
| `defaultContentLanguage` | No | Recommended if you use i18n |
| `outputs.home` | Yes | Must include `JSON` for the search index |
| `taxonomies.tag` | Yes | Enables tag pages |
| `menu.main` | Yes | Header navigation |

### Theme params

| Param | Type | Default | Used for |
| --- | --- | --- | --- |
| `description` | string | `""` | Footer text and meta description fallback |
| `tagline` | string | `""` | Home page subtitle |
| `author` | string | `""` | Footer credit |
| `authorBio` | string | `""` | Footer bio block |
| `footerNote` | string | `""` | Optional footer attribution override |
| `email` | string | `""` | Footer mail link |
| `website` | string | `""` | Footer website link |
| `socialLinks` | array | `[]` | Footer social links |
| `favicon` | string | `""` | Optional favicon path |
| `dateFormat` | string | `"02 Jan 2006"` | Date display format |
| `showTags` | bool | `true` | Show tags on article pages |
| `googleAnalyticsID` | string | `""` | Fallback GA4 measurement ID |

### Social links format

```toml
socialLinks = [
  { name = "GitHub", url = "https://github.com/username" },
  { name = "Mastodon", url = "https://example.social/@username" }
]
```

### Google Analytics and GDPR

The recommended config is:

```toml
[services]
  [services.googleAnalytics]
    ID = "G-XXXXXXXXXX"
```

The theme shows a cookie consent banner and only loads Google Analytics after the visitor accepts analytics cookies. If you prefer, you can also set `params.googleAnalyticsID` as a fallback, but `services.googleAnalytics.ID` is the preferred Hugo-native option.

---

## Development

To preview the theme using the bundled example site:

```bash
cd exampleSite
hugo server --themesDir ../..
```

To build the example site:

```bash
cd exampleSite
hugo --minify --themesDir ../..
```

---

## Customizing colors

Edit `assets/css/main.css` to change the palette.

---

## Language support

English and Italian are built in. Add new languages by creating a new file in `i18n/` and setting the matching `defaultContentLanguage` / `languages` config in your site.

---

## License

[CC-BY-4.0](LICENSE.md) (Creative Commons Attribution 4.0)

© 2024 carmelolg
