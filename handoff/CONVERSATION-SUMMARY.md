# Portable conversation summary — Kuntroversie

Prepared 30 October 2026, Asia/Katmandu. This is a curated working-context summary, not a verbatim transcript or native chat-session export. It omits passwords, API keys and authentication codes.

## Owner's objective

Build and maintain a premium designer-fashion WordPress site that preserves the original Kuntroversie HTML/CSS/JS appearance and full motion, while being genuinely editable through Elementor, integrated with Blocksy and WooCommerce. The owner now wants to continue from Codex on Kali Linux using the GitHub backup, away from the original Windows computer.

## Original source and early work

- Original source supplied as `web CODE-USE-20260928T153801Z-1-001.zip`, later an extracted Downloads folder with the same base name.
- Initially ran as static pages through file URLs and port 8765. Repeated user reports concerned screen flicker and animation problems.
- Subsequently rebuilt into WordPress at `http://localhost/kuntroversie/`.
- The owner explicitly rejected a simple HTML/shortcode code-port as an Elementor rebuild. Required genuine editable widgets/containers, Blocksy integration, a global Kuntroversie plugin, WooCommerce data and a child theme.
- The owner rejected reduced-motion as the forced default experience. Preserve full original motion as an explicit visitor preference while retaining the reduced-motion option for other visitors.

## Binding design and architecture decisions

1. Preserve the original composition, imagery, type identity and authored animation timings.
2. Use actual Elementor containers/widgets and editable controls; no whole-page HTML/shortcode substitute.
3. One shared Blocksy header/footer and one shared global plugin; avoid duplicated page headers/footers.
4. Blocksy child theme retained. WooCommerce owns product names, images, prices, sizes, stock, checkout, accounts and orders.
5. Preserve owner edits and existing store data; back up changes.
6. No Vue, rebranding, fabricated product/merchant information, live payment activation or authentication changes inferred from general polish requests.

## Payment work already completed

- Stripe test mode and a temporary US PayPal Business sandbox merchant were connected for QA, with the owner's authorization.
- Fresh sandbox capture, decline/cancellation and full-refund tests succeeded on 25 October 2026. No real funds moved.
- The PayPal test fixture does not establish real merchant eligibility or change the owner's business country.
- Public HTTPS webhooks and production payment configuration remain separate checks. SMTP/email delivery previously failed locally; do not claim those are working without new evidence.
- Payment secrets and account credentials are in the encrypted migration snapshot, not in this summary. Do not publish or print them.

## 29 October: artisan envelope correction

The owner reported overlapping letters/cards on `/artisans/`. Both letter sections were corrected:

- Identical open/closed footprints to prevent page movement.
- Separate image and caption space; three cards no longer cover one another.
- Container-based narrow layouts instead of viewport-only assumptions.
- More visible closed envelopes and restrained pointer movement.
- Preserved original artwork and unfold timings; click, Enter, Space and Escape worked.
- Measurements at 320, 375, 768, 1024 and 1280px found no settled card/caption overlaps or horizontal overflow.

Relevant installed files are `wp-content/plugins/kuntroversie-site/assets/css/native-widgets.css` (and generated full-motion sibling) and `assets/js/native-widgets.js`.

## 30 October: mobile shopping corrections

- Product size selection previously truncated “Choose an option” when quantity/price/size shared a narrow row.
- At 600px and below the size field now uses a separate row; desktop keeps the original option row.
- Quantity buttons have 44px mobile targets. Shop Kart controls have an extended touch area without oversized visible labels.
- Product families and responsive widths were checked. Existing navigation coming-soon items intentionally show feedback; they were not silently redirected or removed.

## 30 October: designer-brand refinement

The owner requested a premium-fashion critique and then authorized careful improvements without making the site look worse. Implemented:

- Initially visible, still collapsible product descriptions.
- Remove only exact duplicate standalone materials paragraphs from the displayed description; underlying Woo text remains unchanged.
- Clear “Select size” prompt scoped to the real Woo variation form.
- Discreet product links to craftsmanship, delivery, returns and personal assistance.
- Elementor controls for description state, prompt, assistance visibility, link labels and destinations.
- Editable “Explore the collection” link below the homepage film, separate from its play control/artwork.
- More readable product/shop metadata, mobile name/variant spacing and left-aligned product reading text.
- Shared footer links at 11px and larger subscription controls.
- Original photographs, film/letter mechanics, full-motion scripts/timing, saved Elementor documents and merchant settings preserved.

Latest local verification: 306 HTTP/source checks across 17 routes, 73 Elementor component checks, 29 catalogue checks, three upload-package checks. Nine routes screened at 320/768/1280px without horizontal overflow or broken completed images. Size selection, quantity, disclosure, gallery next/previous and new collection link worked. These are scoped local checks, not proof of live-hosting readiness.

## Work explicitly deferred

The owner asked what more could improve the brand. Suggested better real garment photography, model measurements/sizes worn, care instructions, fuller Series/lookbook shopping links, personal consultation, branded metadata/emails and live-host checks.

When asked for confirmed care, model, production/dispatch, shipping rates and hosting details, the owner replied: “we do it later for now” and redirected the task to GitHub backup and Kali handoff. No additional editorial feature changes were implemented after that redirection. Do not assume the unfinished proposals are already built or that the owner supplied their missing facts.

## GitHub transfer

- Repository selected from the owner's open Brave tab: https://github.com/Aishpra/Kuntrooversie
- Public repository, previously empty.
- Branch: `codex/wordpress-backup`.
- Complete backup commit: `ea062adb89fad3c4d90a0663eee1af78831eed5d` (later commits may add handoff documentation).
- The owner insisted on the complete site/database/uploads, not a sanitized design-only export. Therefore the verified full private ZIP was placed inside header-encrypted RAR5 volumes before upload.
- All four encrypted volumes are present on GitHub. Archive extraction test passed and remote Git commit matched the local commit.
- The archive password was supplied separately in the private chat. It must never be added to this public repository.

## What to do on Kali

Read `CURRENT-STATE.md` and `START-HERE.md`. Clone/download the repo, obtain the backup password privately, verify all volume hashes, extract outside any public web root, and restore into a local test WordPress stack. Adapt Linux paths, credentials and URL references without losing serialized Elementor/Blocksy settings or attachment encryption salts. Verify the restored site before making further changes or configuring hosting.
