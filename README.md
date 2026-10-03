# Insight - Technology & Ideas

![HTML5](https://img.shields.io/badge/HTML-5-E34F26)
![CSS3](https://img.shields.io/badge/CSS-3-1572B6)
![JavaScript](https://img.shields.io/badge/JavaScript-none-lightgrey)

An editorial-style homepage for a fictional digital magazine covering technology, AI, design, and startups, built with static HTML5 and CSS3. The page recreates the layout patterns of a modern publication: a cover-story hero, a mixed-size featured grid, a scrolling news ticker, a content-plus-sidebar section, and a category browse grid.

## Live Demo

[https://stackiid.github.io/insight-magazine/](https://stackiid.github.io/insight-magazine/)

## Table of Contents

- [Features](#features)
- [Page Sections](#page-sections)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Design System](#design-system)
- [Responsive Design](#responsive-design)
- [Accessibility](#accessibility)
- [SEO](#seo)
- [Performance Considerations](#performance-considerations)
- [Known Limitations](#known-limitations)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Features

- Sticky primary navigation with a date stamp, centered logo, search and bookmark icons, and a Subscribe button
- Secondary category navigation row (Technology, Artificial Intelligence, Design, Startups, Hardware, Culture, Opinion, and a highlighted "This Week" link) that scrolls horizontally on narrow screens
- Full-width cover-story hero with a gradient overlay, issue tag, headline, deck, byline, date, and read time
- Featured grid with one large card beside two stacked smaller cards
- Breaking-news ticker that scrolls continuously using a CSS keyframe animation on a duplicated content track, and pauses on hover
- "Latest" article list with image, category, headline, summary, author, date, and read time
- Sidebar with a numbered Trending list, an Editor's Pick card, and a newsletter signup block; the sidebar stays in view while scrolling on wide screens
- "Explore" category grid with background images, headline callouts, and article counts for AI, Design, Startups, and Hardware
- Multi-column footer with a tagline, social icons, three link groups, and legal links
- Staggered fade-in entrance animations on the hero and cards
- Reduced-motion support that shortens animations and transitions for users who request it

## Page Sections

| Order | Section | Content |
| --- | --- | --- |
| 1 | Navigation | Date, logo, search, bookmark, Subscribe, category links |
| 2 | Hero | Cover story: "The Intelligence Architects" |
| 3 | Featured | One large card and two small cards |
| 4 | Ticker | Six breaking-news headlines, repeated for a seamless loop |
| 5 | Latest | Four article rows and a Load More Stories button |
| 6 | Sidebar | Trending (five items), Editor's Pick, The Weekly Brief newsletter |
| 7 | Explore | Four category blocks |
| 8 | Footer | Brand tagline, Topics, Company, and Readers link groups, legal links |

## Tech Stack

| Category | Technology |
| --- | --- |
| Markup | HTML5 with semantic elements (`nav`, `section`, `main`, `aside`, `article`, `footer`) |
| Styling | Hand-written CSS3 with custom properties, Grid, Flexbox, `clamp()`, keyframe animations, and `position: sticky` |
| Fonts | Google Fonts: Cormorant Garamond (serif) and Syne (sans-serif) |
| Icons | Font Awesome 6.5.0, loaded from cdnjs |
| Images | Photographs loaded from Pexels URLs, plus a local favicon |
| JavaScript | None |
| Build tooling | None |

## Project Structure

```text
insight-magazine/
|-- assets/
|   |-- favicon.png            # Browser tab icon
|   `-- insight-magazine.png   # Full-page screenshot of the homepage
|-- styles/
|   `-- style.css              # All styles: tokens, layout, components, animations, responsive rules
|-- index.html                 # Complete page markup
`-- README.md
```

## Prerequisites

- A modern web browser
- An internet connection, because the fonts, icons, and photographs are loaded from external hosts
- Optional: Python 3, if you want to serve the site through a local web server

## Getting Started

Clone the repository and move into it:

```bash
git clone https://github.com/stackiid/insight-magazine.git
cd insight-magazine
```

Open `index.html` directly in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

There are no dependencies to install and no build step.

## Design System

The stylesheet is organized into numbered sections, and its design tokens are declared as CSS custom properties on `:root`.

| Group | Examples |
| --- | --- |
| Colors | `--bg`, `--bg-alt`, `--surface`, `--ink-primary`, `--ink-secondary`, `--ink-muted`, `--accent`, `--accent-dark`, `--accent-warm`, `--border` |
| Typography | `--font-serif` (Cormorant Garamond), `--font-sans` (Syne) |
| Layout | `--max-width` (1240px), `--gutter`, `--section-gap` |
| Motion | `--t-fast`, `--t-mid`, `--t-slow` |
| Depth | `--shadow-sm`, `--shadow-md`, `--shadow-lg`, `--shadow-lift` |

Class names follow a block-element-modifier style, for example `card--large`, `article-row-cat--ai`, and `cat-block--design`. Each topic (AI, Design, Startups, Hardware) has its own category modifier class for color treatment.

## Responsive Design

The layout adapts at three max-width breakpoints:

| Breakpoint | Behavior |
| --- | --- |
| 1100px and narrower | The sidebar narrows to 280px, the featured grid becomes two columns with the large card spanning both, the category grid becomes two columns, and the footer stacks with a three-column link area |
| 860px and narrower | The date stamp is hidden, the hero height is reduced, the featured grid and the content-plus-sidebar layout become single columns, the sidebar is no longer sticky, and the footer links use two columns |
| 600px and narrower | Navigation padding and category link size shrink, the hero deck is hidden, article rows use a compact 100px image, the category grid becomes one column, and the footer bottom bar stacks |

The hero headline also scales fluidly with `clamp()`.

## Accessibility

Implemented practices visible in the code:

- `lang="en"` on the root element
- Semantic landmarks with matching `aria-label` values, plus `role="navigation"` and `role="contentinfo"`
- `aria-label` on icon-only links such as Search, Saved articles, and the social icons
- `aria-hidden` on decorative icons and separators
- Descriptive `alt` text on every image
- `tabindex="0"` on cards, article rows, and trending items so they can be reached by keyboard
- Visible `:focus-visible` styles for links, buttons, inputs, and focusable elements
- A `prefers-reduced-motion` rule that shortens animations and transitions
- `<time>` elements with `datetime` attributes for dates

No accessibility audit or WCAG conformance level is claimed.

## SEO

The `<head>` of `index.html` contains:

- A page title
- A viewport meta tag
- A favicon link

The page does not include a meta description, Open Graph tags, a canonical URL, a sitemap, or `robots.txt`.

## Performance Considerations

- The site ships no JavaScript and no build output
- Article images below the hero use `loading="lazy"`, and the hero image uses `loading="eager"`
- Google Fonts are requested with `preconnect` hints and `display=swap`
- Images do not declare `width` and `height` attributes, so layout may shift while they load
- `assets/insight-magazine.png` is a screenshot used only for documentation and is not loaded by the page

## Known Limitations

- Every link uses a `#` placeholder, including navigation, article, footer, and social links
- The Subscribe button, Search and bookmark icons, Load More Stories button, and newsletter input are not connected to any functionality; the newsletter fields are not inside a `<form>` element
- The date in the navigation bar ("Tuesday, May 5, 2026") is written directly into the markup
- All articles, bylines, dates, statistics, and headlines are invented sample content, and several headlines name real companies and people; replace them before using the layout for anything public
- The "Breaking" ticker is marked with `role="marquee"` and moves continuously, with no pause control other than hovering over it
- Photographs depend on Pexels URLs and will not load without an internet connection

## License

No license file is included in this repository, so no license is granted by default. Add a `LICENSE` file to specify the terms under which the code may be used.

## Acknowledgements

- Photographs from [Pexels](https://www.pexels.com)
- Typefaces from [Google Fonts](https://fonts.google.com): Cormorant Garamond and Syne
- Icons from [Font Awesome](https://fontawesome.com)
