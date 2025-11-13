# Documentation Site HTML Prompt

Adopt the mindset of a design systems engineer shipping a comprehensive documentation portal. Generate a **fully formed HTML5 document** with inline styles and lightweight scripts that balances readability, discoverability, and long-term maintainability.

## Purpose & Audience
- Educate developers on platform APIs, components, and release cadence.
- Serve both newcomers onboarding to the product and expert users seeking specific answers fast.
- Enable effortless navigation across large content sets with persistent wayfinding cues.

## Structural Requirements
1. `<head>` containing SEO metadata, Open Graph tags, canonical URL placeholder, search indexing directives, typography preloads, and docsearch meta tags.
2. Global skip link, followed by a sticky `<header>` with product logo, site title, universal search (with keyboard shortcut hint), theme toggle control, and language switcher stub.
3. Responsive navigation layout:
   - Left sidebar `<nav>` with nested lists for sections/topics; collapses into an accessible drawer on mobile and reveals active trail indicators.
   - Main content `<main>` featuring:
     - Hero introduction with value statement, quickstart buttons, latest version badge, and release cadence summary.
     - Release highlights card summarizing recent changes with semantic `<time>` usage and links to changelog entries.
     - Two detailed documentation chapters including headings, descriptive copy, step lists, and code samples with syntax highlighting classes plus copy-to-clipboard buttons.
     - Callout blocks for tips, warnings, and best practices using utility classes with iconography placeholders.
     - Tabbed interface toggling between “Overview” and “API Reference” content, each containing nested headings and anchor links.
     - API reference table summarizing endpoints, methods, and rate limit notes.
   - Right sidebar `<aside>` with an auto-updating “On this page” table of contents, using pure CSS fallback plus JS enhancement for scrollspy and progress indicator.
4. Footer containing feedback CTA, status badge, community links, licensing information, and docs version switcher stub.
5. Persistent support widget zone (can be minimized) offering contact options and SLA notice for enterprise readers.

## Visual & Typographic Guidance
- Limit content width to ~70ch for readability; implement fluid type via `clamp()` and generous line heights.
- Establish CSS variables for color roles, spacing, typography, and elevation; provide `[data-theme="dark"]` variants and high-contrast mode overrides.
- Apply subtle background textures (gradients, masks) to differentiate navigation vs. content areas without harming contrast.
- Style code blocks with a legible monospace font stack and highlight key lines using data attributes.
- Ensure inline code and keyboard shortcuts use distinct visual treatments.

## Interactivity & Enhancements
- Use an IIFE to manage: sidebar drawer toggle with focus trap, theme persistence via `localStorage`, tab switching logic, code copy buttons, and scrollspy activation (with IntersectionObserver fallback to throttled scroll listeners).
- Ensure search input reveals helper text when focused and supports the `/` shortcut to focus.
- Provide anchor link buttons for headings to improve deep linking.
- Defer heavy enhancements until after `DOMContentLoaded` and guard for JavaScript-disabled environments with graceful degradation.
- Expose a lightweight search suggestions dropdown that displays trending queries and supports arrow key navigation.

## Accessibility & Trust
- Enforce semantic heading hierarchy; only one `<h1>`.
- Add ARIA roles/labels for navigation, search, and tab panels; ensure `aria-selected`/`aria-controls` states remain synchronized.
- Include descriptive alt text for illustrative icons or diagrams (use inline SVG with `<title>`/`<desc>`).
- Guarantee keyboard operability for all interactive components and visible focus rings that meet contrast standards.
- Provide breadcrumb navigation with `aria-label="Breadcrumb"` to orient users within multi-level docs.

## Content Expectations
- Supply real instructional copy describing at least one API method, parameters, response example, error handling guidance, and use-case narrative.
- Populate changelog with believable version numbers/dates and link to release notes.
- Add inline comments before major regions (`<!-- Region: Navigation -->`) and note placeholders for translation/localization keys.
- Include sample community question or support pathway callout to encourage user feedback.
- Document at least one migration guide snippet (e.g., “From v2 to v3”) with bullet steps and code diff summary.

## Versioning & Localization
- Present a language switch stub that illustrates how to swap content using `lang` attributes and mirrored layout direction when necessary.
- Add a release timeline mini table referencing semantic version numbers, dates, and support windows (LTS vs current).
- Annotate strings that require localization with `data-i18n` attributes and include guidance for pluralization/variables.
- Provide metadata placeholders for canonical URLs per language and ensure the `<html>` tag exposes `lang` plus `dir` when locales demand RTL support.

## Resilience & Edge Cases
- Demonstrate empty state copy for when API reference data has not loaded; include fallback messaging and support links.
- Offer print styles that expand accordions, reveal full navigation, and render code blocks with contrasting backgrounds.
- Supply CSS to gracefully handle extremely long method names or deeply nested navigation without breaking layout (e.g., `text-wrap: balance`).
- Include a note explaining how to inject deprecation banners at the top of articles, ensuring ARIA live regions announce critical updates.

## Output Instructions
- Return only HTML (no markdown fences) with consistent 2-space indentation.
- Keep script and style blocks organized with section headers for maintainers.
- Conclude with an HTML comment summarizing extension ideas (search integration, analytics hooks, etc.) and documentation analytics to wire up (search queries, top pages).
