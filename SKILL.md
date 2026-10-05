---
name: web-builder
description: >
  Compose website-builder-quality pages for this app: a real canvas, constrained
  components, breakpoints, tokens, and a publish step. Use when building or
  restyling a page that should feel assembled rather than dumped — especially
  community profiles, stalls, directories, and other multi-zone layouts.
metadata:
  short-description: "Page composition distilled from the ten strongest open-source website builders"
user-invocable: false
---

# Web builder

Use this when a surface should feel like it was composed, not stacked. ObzueAI Independent
stalls and member profiles are the reference implementation.

The rules below are an original synthesis of public product behavior from the
ten highest-star website/page builders on GitHub as of October 2026. Do not
copy their code, names, or brands into the app.

## The ten

| Project | Stars | What to keep |
|---|---:|---|
| [GrapesJS](https://github.com/GrapesJS/grapesjs) | 26,290 | Separate content, style, and assets. A block is a thing with a job. |
| [Puck](https://github.com/puckeditor/puck) | 13,419 | The canvas renders real components. The saved document is data, not a screenshot. |
| [Webstudio](https://github.com/webstudio-is/webstudio) | 9,027 | Every zone has a real breakpoint story. Accessibility is part of the canvas. |
| [Instatic](https://github.com/CoreBunch/Instatic) | 8,861 | Publish clean output. The builder chrome does not ship inside the page. |
| [Craft.js](https://github.com/prevwong/craft.js) | 8,758 | Drop rules: a zone only accepts components that belong there. |
| [Elementor](https://github.com/elementor/elementor) | 7,085 | Edit on the page itself. Content, style, and advanced stay in separate controls. |
| [Plasmic](https://github.com/plasmicapp/plasmic) | 7,067 | Tokens and variants. A visual change must not fork a second design system. |
| [blocks](https://github.com/blocks/blocks) | 5,097 | The source of truth stays readable. No mystery layout. |
| [Microweber](https://github.com/microweber/microweber) | 3,440 | Commerce lives in the same page as the story, not in another product. |
| [Frappe Builder](https://github.com/frappe/builder) | 2,411 | Preview the real breakpoints while editing, then publish that exact page. |

## How to compose a page

1. **Zones, in order.** A member page is four zones: banner, identity (portrait + name), actions, catalog. Do not put the form in the banner.
2. **One component owns each zone.** Banner art, portrait, follow, and the music list are separate. They share tokens from `src/styles.css`.
3. **Constraints, not free placement.** Members pick a plate id from `src/lib/identity.ts`. They do not paste arbitrary image URLs.
4. **The preview is the page.** On `/profile`, the stage at the top is the public card. Editing the name, bio, banner, or portrait updates that stage before save.
5. **Breakpoints.** At ~390px the banner is `h-48`, the portrait overlaps it, the name truncates, and actions wrap. At `sm` and up the banner becomes `h-72`. No horizontal scroll.
6. **Directory interaction.** `/artists` is a stage plus a wall. Hover or focus previews a member in the stage. Click opens the stall. That is the builder's "select on canvas" move, done with real links.
7. **Catalog stays on the stall.** Music, merch, and the note form are tabs on the same page, not three more marketing sections.
8. **Publish is save.** Nothing is public until `saveProfile` writes the plate ids and, for a stall, copies them onto the artist row.

## Do not

- Do not add a drag-and-drop editor, a second theme, or a freeform absolute canvas.
- Do not store remote image URLs from the member. Plates are local. House art is a fixed file map.
- Do not put follower emails, private statements, or assistant notes on the public stage.

Read `references/attributes.md` for the longer attribute list.
