# Draw Prompt Library

A curated collection of production-ready prompt templates for generating premium HTML experiences with large language models or autonomous agents. Each Markdown file captures the tone, structure, accessibility, and implementation guidance required to ship polished, modern, and reliable interfaces on demand.

## Available Prompts
| File | Purpose | Signature Highlights |
| --- | --- | --- |
| `landing_page_prompt.md` | Marketing landing page with persuasive storytelling, conversion-oriented CTAs, and responsive hero design. | Conversion funnels, testimonial systems, pricing toggles, adaptive theming. |
| `dashboard_page_prompt.md` | Analytics dashboard emphasizing clarity, interactivity, and theme flexibility across breakpoints. | KPI strip, modal workflows, live regions, enterprise theming tokens. |
| `documentation_page_prompt.md` | Developer documentation shell with evergreen navigation, versioning surface, and code-focused readability. | Scrollspy-enabled TOC, tabbed interfaces, release highlights, syntax-ready blocks. |
| `ecommerce_product_page_prompt.md` | Luxury e-commerce product detail experience with narrative merchandising and trust-building UI. | Carousel + toast pattern, structured data, conversion safeguards, premium storytelling. |

## Quick Start
1. **Identify the archetype.** Choose the Markdown file that matches your desired experience from the table above.
2. **Load the template verbatim.** Provide the full file content to your agent or LLM as the system prompt so expectations are unambiguous.
3. **Append brand specifics.** After the template, list product facts, tone preferences, asset URLs, or analytics requirements that are unique to your build.
4. **Request raw HTML output.** Instruct the model to respond with a single HTML document—no Markdown fences, code blocks, or commentary.
5. **Validate and iterate.** Run the generated output through your accessibility, performance, and design review workflows before shipping.

### LLM Prompting Best Practices
- **Keep instructions atomic.** Feed the template as the system message, then stream brand and product context as a user message. Avoid blending structural guidance with copy points in the same block.
- **Protect tone and scope.** Explicitly ask for “production-grade HTML” and state “no extra commentary” to prevent meta output. If the model drifts, resend the template verbatim.
- **Version your prompts.** Store prompt revisions in source control, tagging them with semantic versions so downstream teams can pin against a known blueprint.
- **Review token budgets.** These templates fit inside GPT-4 class windows with comfortable margins; if you append lengthy product catalogs, chunk them and iterate by section.

### Visual Language Tokens
| Token | Purpose | Notes |
| --- | --- | --- |
| `--color-primary` | Hero CTAs, primary gradients | Provide both light and dark variants to avoid blown-out contrast. |
| `--color-accent` | Badges, data highlights | Reserve for scarce emphasis so analytics states read crisply. |
| `--font-display` | Headline typography | Pair a high-contrast display face with a reliable sans-serif fallback. |
| `--radius-lg` | Cards, modals | Maintain consistency across prompts so rounded corners feel intentional. |
| `--shadow-elevated` | Hover depth, floating panels | Keep blur radii soft and layer with subtle backdrop filters. |

### Integration Playbook
1. **Assemble brand tokens.** Map existing design system colors, typography, and shadows onto the variables defined in each template.
2. **Wire analytics early.** Add data-layer pushes, tracking IDs, and consent banners directly inside the HTML before QA to avoid regressions.
3. **Localize responsibly.** Externalize strings into translation files; preserve aria-label intent and section comments for future editors.
4. **Instrument accessibility.** Run automated checks (Pa11y, Axe) in CI and schedule manual keyboard sweeps before launch.
5. **Capture regressions.** Pair with visual diffing (Percy, Chromatic) so layout fidelity remains intact as prompts evolve.

### Programmatic usage example
```python
from pathlib import Path
import openai

prompt = Path("landing_page_prompt.md").read_text(encoding="utf-8")
brand_context = """\
Brand: NimbusShift (AI workflow automation)\nPrimary CTA: Start free trial\nSecondary CTA: Book a live demo\n"""

completion = openai.ChatCompletion.create(
    model="gpt-4.1",
    messages=[
        {"role": "system", "content": prompt},
        {"role": "user", "content": brand_context},
    ],
)

html = completion.choices[0].message["content"]
Path("landing.html").write_text(html, encoding="utf-8")
```

## Quality Pillars Baked In
- **Visual refinement:** Layered gradients, glassmorphism, and fluid type scales balanced with pragmatic layout grids.
- **Accessibility-first:** Semantic structure, ARIA guardrails, focus management patterns, and respect for user motion preferences.
- **Performance aware:** Self-contained documents, lazy-loading strategies, progressive enhancement, and minimized script surface area.
- **Operational reliability:** Explicit section ordering, believable microcopy prompts, inline documentation, and final delivery checklists.

## Review Checklist
- [ ] Validate HTML and CSS via automated linters or the W3C validator.
- [ ] Audit color contrast and focus order with tooling such as Axe or Lighthouse.
- [ ] Exercise all interactive controls using keyboard-only navigation.
- [ ] Swap in real imagery/assets to confirm layout resilience.
- [ ] Capture screenshots across key breakpoints before publishing.

## Extending the Library
To introduce a new archetype, mirror the structure of the existing templates: start with a role description, document audience and goals, enumerate layout and interaction requirements, outline reliability safeguards, and finish with delivery instructions. Pull requests that keep instructions precise, testable, and implementation-minded are welcome.

When adding a template, also update the table above with a concise summary of what makes the prompt distinctive so consumers can select the right blueprint quickly.

## Changelog
- **v1.2.0** — Added cross-cutting best practices, visual language token guidelines, and integration playbook to keep generated HTML aligned with enterprise delivery standards.
- **v1.1.0** — Introduced detailed structural checklists across landing, dashboard, documentation, and e-commerce templates.
- **v1.0.0** — Published the initial prompt library and README overview.
