# E-commerce Product Page HTML Prompt

Step into the role of a luxury brand UX lead and front-end specialist delivering a premium product detail experience. Output a **single, deploy-ready HTML5 document** with inline CSS and purposeful JavaScript that feels immersive, trustworthy, and optimized for conversion.

## Product Context
- Hero product: premium wearable smart ring with wellness intelligence.
- Audience: style-conscious professionals who value data-backed insights.
- Brand voice: elegant, confident, service-oriented.

## Required Page Flow
1. `<head>` enriched with SEO metadata, Open Graph tags, structured data hints, preconnects for fonts, favicon references, and preload for hero media.
2. Transparent `<header>` with brand mark, navigation, utility links, announcement bar, and a mobile-friendly drawer menu. Header should gain a solid background and drop shadow on scroll.
3. Hero showcase:
   - Left: image carousel within `<figure>` containing multiple `<img>` placeholders, thumbnail strip, zoom affordance, and AR view toggle stub.
   - Right: product name, subheadline, price, reviews summary, availability badge, color/size selectors, payment option icons, trust microcopy, sustainability badge, and dual CTAs (“Add to cart”, “Book a styling session”).
4. Sensory storytelling section with alternating media/text rows, highlighting lifestyle benefits, differentiators, and material callouts.
5. Data insights area featuring wellness metrics cards, radial progress visualizations (SVG), descriptive copy tying metrics to real value, and personalization hook note.
6. Comparison table benchmarking against two competitors with column highlights for key advantages and toggles for spec categories.
7. Customer stories slider with portrait photography placeholders, quote pull-outs, attribution details, and rating breakdown chips.
8. Editorial content row featuring expert review snippet, press logo strip, and behind-the-scenes video placeholder.
9. Support center band including FAQ accordion, contact CTA, live chat teaser, and shipping/returns quick facts.
10. Footer with subscription form, social proof badges, sustainability statement, store locator, localized phone support, and legal links.
11. Sticky bottom action bar on mobile summarizing price, variant selection, and CTA duplication for quick purchase access.

## Visual & Motion Direction
- Employ a dark, cinematic palette with gold/amber accents; define color tokens in `:root` and provide `[data-theme="light"]` fallback along with high-contrast override tokens.
- Layer gradients, soft glows, and glassmorphism panels to create depth while preserving legibility.
- Use `"Poppins", "Helvetica Neue", sans-serif` with `clamp()`-based type scale and generous letter spacing for headings.
- Animate carousel transitions, sticky header reveal, and toast confirmations with `cubic-bezier(.4,0,.2,1)` easing; disable excessive motion per `prefers-reduced-motion`.
- Incorporate parallax or depth cues using CSS perspective for hero imagery, with graceful fallbacks if unsupported.

## Functionality & Behavior
- Implement carousel controls (prev/next buttons, thumbnail click) and update the featured image accordingly.
- Persist selected color/size state; reflect inventory messaging (e.g., “Only 3 left in Midnight Onyx”) and disable unavailable variants.
- Trigger an accessible toast notification on “Add to cart” with `aria-live="polite"` and auto-dismiss.
- Handle header background swap on scroll and store theme preference in `localStorage`.
- Lazy-load secondary imagery with `loading="lazy"` and `decoding="async"`.
- Provide quick-add mini-cart drawer stub showcasing cart summary and loyalty points reminder.
- Guard against repeated CTA clicks with temporary disabled state and spinner feedback.
- Include a “See it in AR” launcher stub that opens a modal explaining device compatibility and provides QR code placeholder.
- Outline gift messaging flow and engravings note with form fields that stay collapsed until toggled.

## Trust, Accessibility & Compliance
- Embed schema.org `Product` microdata (JSON-LD in `<script type="application/ld+json">`).
- Provide descriptive alt text, label all form controls, and ensure focus visibility.
- Include assurances near CTAs (secure payment, warranty, free shipping/returns) and surface privacy policy links.
- Offer keyboard access to carousel controls, accordions, and navigation menus.
- Display compliance text for payment providers (PCI, GDPR) and include age verification note if applicable.
- Surface social proof metrics with `aria-describedby` for context.
- Add copy for guarantees (30-day returns, two-year warranty) and highlight sustainability certifications with verification links.
- Provide a concise finance/legal disclosure block covering installment partners, tax calculation, and cross-border shipping terms.

## Commerce Edge States
- Show low-stock, out-of-stock, and preorder messaging variations along with CTA behavior for each scenario.
- Include sample validation errors for variant selection and cart submission, with accessible inline feedback and summary alert.
- Demonstrate how to reveal upsell/cross-sell modules when cart value meets thresholds, including placeholder product cards.
- Provide a fallback experience when the video asset fails to load (poster image, retry button, and transcript link).

## Output Checklist
- Return HTML only (no markdown fences) with consistent 2-space indentation.
- Annotate major regions with comments for maintainability.
- Conclude with a short HTML comment listing recommended follow-up integrations (analytics, personalization, etc.) and CRM/marketing automation hooks to configure.
