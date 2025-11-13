# Data Dashboard HTML Prompt

Operate as a senior product designer and front-end architect building an interactive analytics dashboard. Deliver a **complete HTML5 document** with embedded `<style>` and concise `<script>` that looks enterprise-grade, loads fast, and handles key workflows across devices.

## Core Objectives
- Surface mission-critical SaaS metrics with clarity and progressive disclosure.
- Provide a calm yet information-rich aesthetic with dark/light theme support.
- Ensure every component remains usable from widescreen monitors down to 360px mobile layouts.

## Layout Blueprint
1. `<head>` with metadata, responsive viewport, favicons, theme-color declarations, Open Graph tags, and preloaded variable fonts.
2. App shell composed of:
   - Collapsible `<aside>` sidebar containing logo, primary navigation, user summary card, and quick filters with pill toggles.
   - Sticky top bar (`<header>`) housing search, date range controls, notification bell, help shortcut, avatar menu, and global status chip (e.g., “Realtime”).
3. KPI strip with four metric cards (title, value, delta chip, sparkline placeholder) aligned on a CSS grid and annotated with tooltips.
4. Main analytics canvas split into two responsive columns:
   - Left column: line/area chart container with filter chips, legend, data range description, and export buttons.
   - Right column: stacked insight cards for top-performing segments and goal progress with radial progress SVGs and alert states for thresholds.
5. Operational table with sortable headers, status badges, pagination controls, inline filters, and bulk action toolbar with selected count feedback.
6. Incident feed or anomaly callout card summarizing alerts with severity icons and remediation CTA.
7. Insight drawer or modal triggered from “View details” buttons; include overlay, focus trap, close affordances, and audit trail list.
8. Footer summarizing support links, system status, timestamp for last data refresh, and changelog link.
9. Background job heartbeat indicator and “Data freshness” tooltip communicating last ETL sync with timezone clarity.

## Visual System & Theming
- Establish design tokens via CSS variables for color roles, spacing scale, shadows, and typography (`"Inter", "Segoe UI", sans-serif`) plus motion tokens for animation timings.
- Build layouts using CSS grid with `minmax()` and `auto-fit` to reflow cards; include `@media` breakpoints for tablet/mobile.
- Offer dark mode via `[data-theme="dark"]` attribute; ensure tokens respect WCAG contrast.
- Apply neumorphic-inspired depth sparingly (soft shadow pairs + inset highlights) while keeping important controls high-contrast.
- Animate state changes (progress bars, modal entrance) with `cubic-bezier(.4,0,.2,1)` timing and honor `prefers-reduced-motion`.
- Provide print stylesheet adjustments for exporting snapshots (monochrome palette, visible table borders).

## Interaction & Behavior Requirements
- Implement sidebar collapse, theme switch persistence, modal open/close, table sorting, and chart range toggles within a scoped IIFE.
- Provide accessible keyboard support: `Tab` traversal, `Enter`/`Space` triggers, and ESC to close overlays.
- Include live region updates for KPI delta messages and toast notifications (if any).
- Use inline SVGs for charts with `<title>`/`<desc>` to ensure screen reader context.
- Defer non-critical scripts until `DOMContentLoaded` and guard against missing data with safe defaults and inline warnings.

## Content & Copy
- Populate titles, tooltips, filters, and sample metrics with realistic SaaS analytics language—avoid lorem ipsum.
- Add inline comments describing each major component (`<!-- Component: KPI Cards -->`) and note where data should be injected.
- Provide contextual helper text (e.g., “Compared to last sprint”) and action-oriented button labels.
- Surface at least one empty state message and one success toast example to guide future states.
- Include sample copy for anomaly explanations (root cause hints) and recommended next steps for ops teams.

## Data Integrity & Edge States
- Guard charts against missing datapoints by showing dashed placeholders, inline alerts, and explicit “Awaiting data” messages.
- Show skeleton loaders for the KPI strip and tables during initial load; replace with data once the mock script resolves promises.
- Demonstrate pagination boundaries (disabled previous/next) and truncated table rows with tooltips for overflow content.
- Provide a resilient print/export button pattern that warns users when filters reduce row counts below expected thresholds.

## Output Expectations
- Return only HTML markup with consistent 2-space indentation and readable line lengths.
- Keep JavaScript minimal and well-commented for future enhancement, grouping logic under headings within the `<script>` block.
- End the document with a concise comment summarizing outstanding integration tasks (data wiring, auth hooks, etc.) and monitoring hooks to add later.
