# Landing Page HTML Prompt

You are a principal-level product designer and front-end engineer collaborating to deliver a marketing landing page that feels premium, modern, and conversion-focused. Produce a **single, self-contained HTML5 document** with inline `<style>` and minimal `<script>` that is ready for direct publishing.

## Experience Goals
- Inspire confidence in a forward-thinking SaaS platform aimed at tech-savvy decision makers.
- Communicate value quickly with persuasive, benefit-led storytelling and measurable outcomes.
- Maintain a polished, trustworthy aesthetic that works flawlessly across desktop, tablet, and mobile breakpoints.

## Required Structure (in order)
1. `<head>` with descriptive metadata, Open Graph tags, social share image placeholder, favicon link, and preconnect hints for fonts/CDNs.
2. `<header>` with logo, primary navigation, dark/light toggle placeholder, announcement badge, and a right-aligned CTA button.
3. Hero section featuring: standout headline, supporting paragraph, primary and secondary CTAs, bullet proof points, trust badges, and a product mockup frame with caption.
4. Value proposition strip with `<!-- Section: Pain Relievers -->` comment, showcasing 3 friction statements paired with solutions.
5. Key benefits grid (3–4 cards) each containing an icon, concise title, measurable outcome-focused copy, and micro-interaction note.
6. Social proof strip with testimonial slider or grid, star ratings, client logos in muted styling, and a verified-buyer badge pattern.
7. Feature deep-dive chapter using alternating image/text splits plus callout badges for technical differentiators and inline code-style tags for platform names.
8. Interactive metrics section highlighting ROI stats, animated counters, or timeline (CSS-driven, JS-enhanced) and a narrative paragraph interpreting the data.
9. Pricing preview with two tiers (starter vs. growth), toggles for monthly/annual, comparison bullets, and footnotes for billing nuances.
10. Resource row offering webinar, whitepaper, and product tour cards that link deeper into the funnel.
11. FAQ accordion (4 curated questions) using an accessible disclosure pattern with keyboard support and clear state change icons.
12. Final CTA banner reiterating the core value proposition with a secondary contact option and optional scheduling link.
13. `<footer>` including sitemap links, compliance text, newsletter signup, social icons, and a cookie preferences stub.

## Visual & Interaction Guidance
- Define CSS custom properties in `:root` for colors, typography scale, spacing, and shadows; include dark-mode overrides under `[data-theme="dark"]`.
- Employ fluid type/spacing via `clamp()` and responsive CSS grid/flexbox layouts with `minmax()` for card reflow.
- Introduce layered gradients, subtle glassmorphism panels, and depth through soft drop shadows while retaining AA contrast.
- Provide hover/focus states on all interactive elements with `transition: 200ms ease` and active feedback for buttons/links; ensure touch targets are at least 44px.
- Respect `prefers-reduced-motion` by disabling non-essential animations and providing reduced-motion variants.

## Copy & Content Requirements
- Use believable, concise marketing copy—no lorem ipsum. Highlight proof (metrics, testimonials, quotes) and clear CTAs (“Start free trial”, “Talk to an expert”).
- Include inline comments (`<!-- Section: ... -->`) before each major block to aid future edits and annotate any conditional logic.
- Supply placeholder alt text and descriptive captions for mock imagery.
- Draft CTAs with actionable verbs and, where relevant, supporting microcopy (e.g., “No credit card required”).
- Compose headlines with a balance of emotion and specificity; pair each with a supporting line that references measurable business outcomes.
- Provide at least one paragraph addressing security/compliance assurances and another enumerating implementation support options.
- Include sample copy for cookie consent, privacy policy callouts, and newsletter compliance to keep the page legally robust.

## Accessibility, Performance & Reliability
- Maintain logical heading hierarchy (single `<h1>`). Use semantic tags (`<section>`, `<article>`, `<nav>`, `<aside>`).
- Add ARIA labels (`aria-expanded`, `aria-controls`, `aria-live` for status messaging) where appropriate and ensure `role="status"` where passive updates appear.
- Ensure keyboard navigation for menu toggle, accordion, sliders; provide focus outlines.
- Keep JavaScript lean within an IIFE (mobile menu toggle, theme switch persistence via `localStorage`, FAQ interaction).
- Optimize assets: leverage CSS gradients/SVG placeholders, `loading="lazy"` on non-critical imagery, and preconnect hints.
- Provide fallback typography stack using system fonts should custom fonts fail to load.
- Define responsive breakpoints (`@media (max-width: 1024px)` and `@media (max-width: 640px)`) to progressively collapse grids, reposition CTAs, and preserve hierarchy on small screens.
- Include a `prefers-reduced-motion` media query that replaces animated counters with static values and disables parallax treatments.
- Add defensive CSS for extremely long localized strings (e.g., `hyphens: auto`, flexible buttons) to prevent layout breakage.

## Final Delivery Instructions
- Output **only the HTML markup**—no markdown fences or explanatory text.
- Format with 2-space indentation and wrap lines at readable lengths.
- Ensure `<style>` is organized with comment headers for each section and use CSS custom property fallbacks.
- Close with a brief HTML comment summarizing dependencies or follow-up actions for implementers, including analytics or form wiring notes.
