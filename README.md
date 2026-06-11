# Canva Design Director

> Elite Canva MCP skill for professional design creation, brand governance, presentation design, visual storytelling, and anti-AI-slop workflows.

`canva-design-director` is a high-discipline AI design skill for agents that can use the Canva MCP Server. It turns an AI assistant into a senior design director that can plan, generate, refine, resize, review, and export polished Canva assets with strong layout systems, brand governance, accessibility checks, and minimal, intentional visual direction.

This skill is built for creators, marketers, founders, agencies, and AI coding/design agents that need Canva output that feels professional instead of generic.

---

## What This Skill Does

The skill guides an AI agent to create and edit Canva designs using a strict design-director workflow:

- Audits existing brand kits and templates before designing.
- Chooses a proper layout grid before placing elements.
- Uses controlled typography with a maximum of two font families.
- Applies a monochrome + one-accent color system unless a brand kit says otherwise.
- Uses Canva MCP tools for design generation, structured design creation, asset upload, editing transactions, resizing, comments, and exports.
- Enforces accessibility, contrast, safe zones, and delivery checks before handing off work.
- Avoids “AI slop”: clutter, generic 3D assets, excessive gradients, random decoration, poor hierarchy, and unmotivated visuals.

---

## Best Use Cases

Use this skill when you want an AI agent to produce or improve:

- Canva presentations and pitch decks
- Instagram posts, carousels, reels covers, and stories
- Facebook graphics and campaign creatives
- LinkedIn banners and social graphics
- Posters, flyers, brochures, and campaign collateral
- Brand templates and brand-governed assets
- Marketing layouts with clear hooks, value propositions, and CTAs
- Infographics and information design
- Existing Canva design audits and cleanup

---

## Requirements

Before using this skill, you need:

1. **An AI assistant or coding agent that supports skills/custom instructions.**
2. **Canva MCP Server access.**
3. **A Canva account.**
4. **MCP configured in your AI client.**

Canva MCP remote server endpoint:

```txt
https://mcp.canva.com/mcp
```

Example MCP configuration using `mcp-remote`:

```json
{
  "servers": {
    "Canva": {
      "type": "stdio",
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote@latest",
        "https://mcp.canva.com/mcp"
      ]
    }
  }
}
```

After setup, authenticate Canva when prompted by your AI assistant.

---

## Installation

Install directly with `skills.sh` using the standard `skills` CLI:

```bash
npx skills add https://github.com/mavericraven/canva-design-director --skill canva-design-director
```

After installation, restart or reload your AI agent so it can detect the new skill.

You can then invoke it naturally in your prompt:

```txt
Use the canva-design-director skill to create a premium Instagram carousel in Canva.
Check the brand kit first, follow the design-director workflow, and export the final creative as PNG.
```

---

## Repository Structure

```txt
canva-design-director/
├── SKILL.md
├── LICENSE
├── assets/
│   ├── example-brand-systems.md
│   ├── example-information-design.md
│   ├── example-marketing-layouts.md
│   ├── example-slide-structures.md
│   └── example-social-layouts.md
└── references/
    ├── accessibility-standards.md
    ├── anti-ai-slop.md
    ├── asset-selection.md
    ├── brand-governance.md
    ├── canva-mcp-workflows.md
    ├── color-system.md
    ├── design-principles.md
    ├── design-review-checklist.md
    ├── editing-transactions.md
    ├── executive-design-principles.md
    ├── export-standards.md
    ├── layout-system.md
    ├── marketing-design.md
    ├── presentation-frameworks.md
    ├── resizing-guidelines.md
    ├── social-media-specs.md
    └── typography-system.md
```

---

## Core Workflow

The skill follows a design-director process:

### 1. Audit

The agent checks existing Canva brand kits, brand templates, previous designs, and available assets before creating anything new.

### 2. Plan

Before touching the canvas, the agent defines:

- Output format
- Grid system
- Typography palette
- Color approach
- Main focal point
- Visual path
- CTA priority

### 3. Generate

The agent prefers structured design generation for controlled, intentional layouts instead of vague freeform prompts.

Preferred Canva MCP tool:

```txt
generate-design-structured
```

### 4. Refine

The agent uses editing transactions for precise layout corrections:

```txt
start-editing-transaction
→ perform-editing-operations
→ get-design-thumbnail
→ commit-editing-transaction
```

If the design becomes structurally compromised, the transaction should be cancelled and restarted.

### 5. Verify

Before delivery, the agent checks:

- Single clear focal point
- Typography hierarchy
- Grid alignment
- Accessible contrast
- Brand consistency
- Safe zones
- Export format
- No unnecessary decoration

### 6. Export

Recommended export formats:

- **Social / digital:** PNG
- **Presentation / print:** PDF
- **Editable presentation handoff:** PPTX when supported
- **Video / motion assets:** MP4 when supported

---

## Design Rules

The skill is intentionally strict. These are the non-negotiables:

### Layout

- Use a 12-column grid or thirds-based composition.
- Use generous margins.
- Align everything mathematically.
- Use whitespace as structure, not leftover space.
- Prefer asymmetrical balance when it improves visual flow.

### Typography

- Maximum two typeface families.
- Exactly three hierarchy levels:
  - Title
  - Subtitle
  - Body
- Use brand-kit typography when available.
- Fallback typefaces: Inter, Helvetica Neue, or SF Pro.
- Body text should remain readable, with proper line height.

### Color

- Default system: monochrome + one accent.
- Use exact brand-kit hex values when brand rules exist.
- Avoid arbitrary color mixing.
- The CTA should normally have the strongest contrast.

### Imagery

- Use intentional imagery only.
- Avoid generic 3D illustrations unless the brand explicitly calls for them.
- Never float text directly over complex images.
- Use overlays or solid slabs for text legibility.

### Accessibility

- Maintain WCAG AA contrast where possible.
- Do not rely on color alone to communicate meaning.
- Preserve logical reading order.
- Respect social media safe zones.

---

## Canva MCP Tool Guide

| Task | Recommended Canva MCP Tool |
|---|---|
| Create a design from a simple description | `generate-design` |
| Create a controlled layout | `generate-design-structured` |
| Start from a template or brand system | `create-design-from-candidate` |
| Upload images or logos | `upload-asset-from-url` |
| Search existing designs | `search-designs` |
| Edit text, position, color, size, or alignment | `start-editing-transaction` → `perform-editing-operations` → `commit-editing-transaction` |
| Preview the design | `get-design-thumbnail` |
| Inspect full design data | `get-design` |
| Resize for another format | `resize-design` |
| Check export options | `get-design-export-formats` |
| Export the final design | `export-design` |
| Leave design feedback | `comment-on-design` |
| Review comments | `list-comments` |

---

## Social Media Sizes

Common supported design targets:

| Platform | Size |
|---|---:|
| Instagram Square | 1080 × 1080 px |
| Instagram Story / Reel | 1080 × 1920 px |
| X / Twitter Post | 1600 × 900 px |
| LinkedIn Banner | 1584 × 396 px |

Keep important text away from edges, profile overlays, buttons, captions, and app UI areas.

---

## Example Prompts

### Instagram Carousel

```txt
Use the canva-design-director skill to create a 5-slide Instagram carousel for a luxury Maldives resort.
Use a premium editorial style, one clear hook per slide, large typography, spacious layout, and a strong final CTA.
Check brand kit first and use Canva MCP to generate the design.
```

### Facebook Campaign Creative

```txt
Use canva-design-director to create a Facebook post creative for a limited-time resort offer.
Prioritize conversion: hook first, value proposition second, CTA highest contrast.
Use clean typography, no clutter, and export as PNG.
```

### Pitch Deck

```txt
Use canva-design-director to create a 10-slide startup pitch deck in Canva.
Use the Apple Keynote method: one idea per slide, massive typography, strong negative space, and one visual focal point per slide.
```

### Existing Design Cleanup

```txt
Use canva-design-director to audit my existing Canva design.
Remove clutter, fix alignment, improve hierarchy, enforce contrast, and leave comments where changes are needed.
```

### Brand Template

```txt
Use canva-design-director to create a reusable brand-governed social template.
Check brand kit first, use exact colors and fonts, define safe zones, and create a clean layout system for future posts.
```

---

## Anti-AI-Slop Policy

This skill rejects design habits that make AI-generated creative look cheap or generic.

Avoid:

- Random decorative blobs
- Excessive gradients
- Generic 3D objects
- Too many typefaces
- Unclear hierarchy
- Overcrowded layouts
- Weak CTAs
- Poor image masking
- Low-contrast text
- Center-aligned everything
- Design elements that do not serve the message

Operating principle:

```txt
Intention → structure → refinement → verification → delivery.
No decoration without purpose.
```

---

## Delivery Checklist

Before final delivery, confirm:

- [ ] Every page or slide has one clear focal point.
- [ ] Typography uses no more than two font families.
- [ ] The design has exactly three hierarchy levels.
- [ ] Alignments follow a grid.
- [ ] Spacing follows a 4pt or 8pt system.
- [ ] Colors follow the brand kit or monochrome + one accent.
- [ ] Text contrast is accessible.
- [ ] Social designs respect safe zones.
- [ ] CTA is visually dominant where conversion matters.
- [ ] No unnecessary decoration remains.
- [ ] Export format matches the delivery channel.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Canva MCP tools are unavailable | Confirm your AI client supports MCP and the Canva server is configured. |
| Canva asks for authentication | Complete the Canva OAuth/login flow in your AI client. |
| Export fails with licensing issues | Replace restricted assets with brand-owned or royalty-free assets. |
| Design looks generic | Switch from freeform generation to structured layout generation. |
| Layout is cluttered | Remove elements until only one clear focal point remains. |
| Resize breaks the design | Resize first, then run an editing transaction to rebalance the layout. |
| Brand kit is not found | Use the fallback system: Inter/Helvetica/SF Pro, monochrome + one accent. |

---

## Recommended Agent Behavior

When this skill is active, the agent should not immediately generate a design. It should first state the design plan:

```txt
Format: Instagram carousel
Grid: 12-column / 8pt spacing
Typography: Brand font or Inter fallback
Color: Brand palette or monochrome + one accent
Focal point: Resort hero image + offer hook
Visual path: Hook → value → CTA
Export: PNG
```

Only after the plan is clear should the agent execute with Canva MCP tools.

---

## License

MIT License. See [`LICENSE`](./LICENSE) for details.

---

## Credits

Created by [mavericraven](https://github.com/mavericraven) for high-quality AI-assisted Canva design workflows.
