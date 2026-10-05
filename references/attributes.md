# Attributes kept from the ten builders

Each line is the behavior worth copying into a hand-built page. None of these
are licenses to vendor their UI or code.

1. **GrapesJS — block model.** A banner is not a background style on a heading. It is its own frame with art, an error fallback, and a label.
2. **Puck — data, not pixels.** A profile stores `banner` and `portrait` plate ids. The React stage renders them. Reloading the page rebuilds the same stage.
3. **Webstudio — CSS is complete and responsive.** Heights, type, and overlap change at the `sm` breakpoint. Focus rings stay visible. Buttons are at least 44px.
4. **Instatic — static result.** House banners are files in `public/community/`. The running page does not call an image model.
5. **Craft.js — parent rules.** The portrait zone only accepts a mark or a portrait file. The banner zone only accepts a wide plate or a banner file. `resolveToken` enforces that.
6. **Elementor — on-canvas edit.** The profile form and the stage are on one screen. The member sees the banner move as they pick a plate.
7. **Plasmic — tokens and variants.** Plates are variants of one system (field, soft, deep, paper, cream, hot). Copper is the only accent.
8. **blocks — readable source.** `IdentityStage` and `MemberCard` are ordinary components. There is no serialized editor JSON in the database.
9. **Microweber — shop in the page.** A stall's music and merch are tabs under the identity, with add-to-basket on the same surface.
10. **Frappe Builder — what you preview is what you open.** The community wall's spotlight uses the same `IdentityStage` as the stall. Hover is not a different design.

## ObzueAI Independent mapping

- Stage: `src/components/identity.tsx` (`IdentityStage`, `MemberCard`, `PlatePicker`)
- Tokens and motion: `src/styles.css` (`.banner-zoom`, `.portrait-live`, `.plate-*`)
- Data: `profiles.banner`, `profiles.portrait`, copied onto `artists` when a stall opens
- Migration: `migrations/0003_identity.sql`
