# 📰 Insight - Technology & Ideas

An editorial-style digital magazine homepage covering technology, AI, design, and startups, built with static HTML5 and CSS3.

<div align="center">

### 🔗 [**View Live Demo**](https://stackiid.github.io/insight-magazine/) 🔗

</div>

---

## 📖 Overview

Insight is a static front-end recreation of a modern tech-and-ideas publication's homepage - the kind of layout you'd see on a digital-first magazine site. It was built as a front-end practice project focused on editorial layout patterns: a cover-story hero, a mixed-size featured grid, a scrolling breaking-news ticker, a two-column content-plus-sidebar layout, and a category browse section, all without a JavaScript framework.

## ✨ Features

- Sticky navigation bar with date stamp, logo, search/bookmark icons, and a subscribe CTA
- Secondary category nav row (Technology, AI, Design, Startups, Hardware, Culture, Opinion, "This Week")
- Full-bleed cover-story hero with gradient overlay, issue tag, and read-time metadata
- Featured articles grid mixing one large card with two stacked smaller cards
- Auto-scrolling breaking-news ticker with a duplicated track for a seamless loop
- Two-column "Latest" article list paired with a sidebar
- Sidebar widgets: numbered Trending list, Editor's Pick card, and a newsletter signup form
- "Explore" category grid with per-topic background images, headline callouts, and article counts
- Multi-column footer with brand blurb, social links, and topic/company/reader link groups

## 🧠 Concepts Demonstrated

| Concept                    | Where it shows up                                                                                             |
| -------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Semantic HTML5             | `<nav>`, `<section>`, `<main>`, `<aside>`, `<article>`, `<footer>` with matching `aria-label`s                |
| CSS Grid & Flexbox         | Featured grid, content + sidebar layout, category grid, footer columns                                        |
| CSS keyframe animation     | Infinite-scroll breaking-news ticker (duplicated content track, no JS)                                        |
| Responsive design          | Layout adapts from multi-column desktop down to a stacked single-column view                                  |
| Accessibility              | `role="navigation"`/`role="contentinfo"`, `aria-label` on every landmark, `tabindex="0"` on interactive cards |
| BEM-style CSS naming       | Consistent `block-element--modifier` naming throughout `styles.css`                                           |
| Third-party integration    | Google Fonts (Cormorant Garamond, Syne) + Font Awesome 6 via CDN                                              |
| Content hierarchy patterns | Distinct visual treatment for cover story vs. featured vs. latest vs. trending content                        |

## 📁 Project Structure

```
insight-magazine/
├── index.html                    # All page markup - nav, hero, featured grid, ticker,
│                                 # latest articles, sidebar, category grid, footer
├── styles/
|   └── style.css                 # All styling - layout, typography, ticker animation, responsive rules
└── assets/
    ├── favicon.png               # Browser tab icon
    └── insight-magazine.png      # Brand asset
```

## 🚀 Getting Started

**Prerequisites:** a web browser. No build tools, no package manager, no dependencies to install.

```bash
# Clone the repo
git clone <your-repo-url>
cd insight-magazine

# Open directly
# Option A - just double-click index.html

# Option B - serve locally (recommended for correct relative paths)
python -m http.server 8000
# then visit http://localhost:8000
```

## 📝 Notes

- All article imagery is pulled from Pexels via direct URLs - swap these for your own assets before production use.
- Every link (`href="#"`), the subscribe button, search/bookmark icons, "Load More Stories," and the newsletter form are static placeholders - none are wired to a CMS, search index, or email service.
- Article headlines, bylines, and dates are illustrative content, not real reporting.
- Future improvement: connect the newsletter form to a real provider (e.g., Mailchimp, ConvertKit) and wire the category/nav links to actual article-listing pages.

## 📄 License

MIT - see the [LICENSE](./LICENSE) file in the root of the repository.
