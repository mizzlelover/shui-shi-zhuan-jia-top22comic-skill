# 谁是专家 · Top22 漫画肖像图鉴设计系统

## 0. Research Log

- Embedded references: shortlisted Pinterest, Wired, and Notion; picked `soft-skill.md` + `pinterest.md` because the page is a visual style archive where artwork should lead and the surrounding interface should feel like a warm editorial collection.
- UI/UX database: searched `portrait art gallery visual discovery image cards`; selected an image-first portfolio grid with neutral surfaces and category filtering.
- Lazyweb: skipped; the task is a branded extension of an existing project, with no external site to reproduce.
- Image drafts: skipped; the 22 approved V2 portrait studies are the visual assets and should remain intact.
- Existing UI: extracted the current gallery's warm paper, ink, rust, searchable cards, and two audience groups; the user asked for a full visual packaging pass, so this document records the shared design before implementation.

## 1. Atmosphere & Identity

The page feels like an independent manga editor's visual archive: warm paper, deep ink, clear editorial typography, and a wall of characterful portrait studies. The signature is a restrained archive frame that lets each of the 22 portraits carry the color and personality. “谁是专家” is the publication identity, not a decorative watermark over the art.

## 2. Color

| Role | Token | Light | Dark | Usage |
| --- | --- | --- | --- | --- |
| Page | `--paper` | `#f4f0e8` | `#171411` | Main canvas |
| Surface | `--surface` | `#fffdf8` | `#211d19` | Cards and reading panels |
| Raised surface | `--surface-raised` | `#ffffff` | `#2c2620` | Search and filters |
| Primary ink | `--ink` | `#211e1a` | `#f2ece5` | Titles and main copy |
| Secondary ink | `--ink-soft` | `#655d53` | `#c4baae` | Descriptions |
| Quiet ink | `--ink-quiet` | `#786f64` | `#aa9f91` | Metadata |
| Hairline | `--rule` | `#ddd4c8` | `#473c32` | Dividers and card edges |
| Control border | `--control-border` | `#9b8b76` | `#8f8171` | Search and recovery control |
| Brand accent | `--cinnabar` | `#a8422b` | `#ec866a` | Primary links and active filter |
| Accent wash | `--cinnabar-wash` | `#f0e0d8` | `#3e2822` | Active filter background |
| Focus | `--focus` | `#3157a4` | `#9ab4ff` | Keyboard focus ring |

Use warm neutrals around images. Cinnabar is reserved for one primary action or selected state; it does not tint the artwork.

## 3. Typography

Use a local Chinese system stack so the page needs no external font request. Display and section headings use `Songti SC`, `Noto Serif CJK SC`, then a serif fallback. Body copy uses `-apple-system`, `BlinkMacSystemFont`, `PingFang SC`, `Noto Sans CJK SC`, then sans-serif.

| Level | Size | Weight | Line height | Usage |
| --- | --- | --- | --- | --- |
| Display | `clamp(42px, 5.8vw, 78px)` desktop; `clamp(30px, 8.5vw, 40px)` compact | 600 | 1.08 / 1.12 | Hero title |
| Card title | `18px` desktop; `17px` compact | 650 | 1.4 | Style card title |
| Body | `17px` | 400 | 1.7 | Intro |
| Secondary | `15px` | 400-650 | 1.5-1.7 | Card details, search, filters, count, and links |
| Label | `15px` | 650-700 | 1.4 | Brand, group, and form labels |
| Index | `12px` | 700 | 1 | Number badges |

## 4. Spacing & Layout

The spacing base is 4px. Shared tokens cover 4, 8, 12, 16, 20, 24, 32, 40, 44, 48, 64, and 88px; local optical offsets are limited to component details. The radius tokens are 12px for controls, 16px for cards, and 999px for circular badges; the hero samples use a tall arch with rounded lower corners. Content uses a centered maximum width of 1440px. The hero pairs an editorial text block with a compact strip of four real style images; the archive uses a dense image-first grid.

Desktop cards: four columns; tablet: three; narrow tablet: two; phone: one. GitHub's rendered Markdown archive uses two columns so image labels remain readable at mobile widths. Images keep a square crop in cards; opening one leads to the original full-resolution PNG.

## 5. Components

### Brand hero
- **Structure**: publication label, headline, one-paragraph promise, primary link, featured image strip.
- **Variants**: full README intro and compact gallery intro.
- **Spacing**: 16px within the copy group, 32px between hero and archive, using the shared spacing scale.
- **States**: links have default, hover, active, and visible keyboard focus.
- **Accessibility**: one H1, descriptive image alternatives, link text names the destination.
- **Motion**: none on load; link color and image scale use the standard transition.
- **Layout**: editorial split on desktop; stacked copy then image strip on mobile.

### Style card
- **Structure**: linked preview image, two-digit number, category, title, short visual signature, full-image link.
- **Variants**: interactive HTML card and rendered GitHub Markdown card.
- **Spacing**: 12px metadata gap, 16px card padding.
- **States**: default, hover on linked images only, pressed, visible keyboard focus; filtered-out cards are removed from layout.
- **Accessibility**: image alt identifies the direction; image and text links reach the same original PNG.
- **Motion**: transform/opacity only, 220ms; disabled under reduced motion.
- **Layout**: responsive CSS grid in HTML; two-column table in GitHub Markdown.

### Search and category filters
- **Structure**: labeled search field followed by three category buttons and a live result count.
- **Variants**: all, shonen/seinen, shojo/josei.
- **Spacing**: 8px between controls; 12px vertical and 16px horizontal control padding.
- **States**: default, hover, pressed, selected, keyboard focus, no-results.
- **Accessibility**: semantic buttons, `aria-pressed`, labeled input, `aria-live` result count, visible focus.
- **Motion**: card disappearance is immediate; no layout animation while typing.
- **Layout**: wraps across rows on narrow screens.

## 6. Motion & Interaction

| Type | Duration | Easing | Usage |
| --- | --- | --- | --- |
| Micro | 120ms | `ease-out` | Press feedback |
| Standard | 220ms | `cubic-bezier(0.2, 0.7, 0.2, 1)` | Image lift and link color |
| Emphasis | 360ms | `cubic-bezier(0.2, 0.7, 0.2, 1)` | Gallery navigation only |

Animate only `transform` and `opacity`. Every control has a visible focus style. Under `prefers-reduced-motion`, remove spatial movement and retain immediate state feedback.

## 7. Depth & Surface

Use tonal shift as the primary depth strategy. Cards sit on warm paper with a fine warm rule and a white image field; avoid heavy drop shadows. Card radius is 16px, image radius is 12px, and control radius is 12px. Keep nested radii concentric.

## 8. Accessibility Constraints & Accepted Debt

Target WCAG 2.2 AA: body-text contrast at least 4.5:1, keyboard access to every link/control, meaningful alt text, semantic headings, responsive zoom, and reduced-motion support. Search and category filters remain usable without hover.

| Item | Location | Why accepted | Owner / Exit |
| --- | --- | --- | --- |
| No in-page full-screen lightbox in GitHub Markdown | `gallery.md` | GitHub renders repository Markdown safely but does not execute repository HTML; each card instead opens GitHub's native full-image preview. The local HTML gallery retains search and filtering. | Project maintainer / revisit if a private, rendered Pages host is available |
