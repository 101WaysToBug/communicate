---
name: communicate
description: Transform any content into polished communication formats — Executive Email, Slack Update, Notion Document, Release Notes, or Product Updates GTM. Use when the user asks to "communicate this", "draft a Slack update", "write an executive email", "create release notes", "draft a GTM update", or needs to format content for stakeholders.
argument-hint: "[content or topic to communicate]"
version: 1.0.0
---

# Communication Style Formatter

Transform any content — research findings, feature updates, status reports, release changes — into one or more polished communication formats.

## Step 1: Determine the Style

Ask the user which communication style(s) they want. Present these options:

1. **Executive Email** — Strategic update for leadership with business impact (3 paragraphs)
2. **Slack Update** — Quick team update, easy to scan (2-4 lines)
3. **Notion Document** — Comprehensive async reference with full context (300-600 words)
4. **Release Notes** — Structured announcement covering: feature name, what's changing and why, who it's for, and how it works (200-500 words)
5. **Product Updates GTM** — Go-to-market update with value prop, target audience, key messaging, rollout plan, and supporting assets needed (300-600 words)
6. **All of the above** — Generate all five styles in a single output

If the user provided `$ARGUMENTS`, use that as the content to communicate. If no arguments are provided, ask the user what content they want to communicate.

## Step 2: Apply the Style

Read the matching style reference(s) from the references directory and follow the format rules exactly:

- [Executive Email style](references/style-executive-email.md)
- [Slack Update style](references/style-slack-update.md)
- [Notion Document style](references/style-notion-doc.md)
- [Release Notes style](references/style-release-notes.md)
- [Product Updates GTM style](references/style-product-updates-gtm.md)

## Style Summaries

### Executive Email
- **Length:** 3 paragraphs (6-8 sentences total)
- **Tone:** Professional, strategic, confident
- **Structure:** What we learned → Why it matters → What we're doing next
- **Include:** Specific numbers, business metrics, competitive context
- **Avoid:** Emojis, casual language, excessive technical details

### Slack Update
- **Length:** 2-4 lines maximum
- **Tone:** Casual, friendly, conversational
- **Emojis:** 1-2 relevant emojis
- **Structure:** Main announcement → Quick context → Next step (optional)
- **Avoid:** Jargon, long paragraphs

### Notion Document
- **Length:** 300-600 words
- **Tone:** Professional but accessible, detailed, well-organized
- **Structure:** Title → Summary (TL;DR) → Sections with H2 headers → Bullets and tables
- **Include:** Full context, supporting details, direct quotes, examples
- **Avoid:** Assuming prior knowledge

### Release Notes
- **Length:** 200-500 words
- **Tone:** Informative, neutral, slightly celebratory for big features
- **Structure:** Feature name → What's changing and why → Who is this for → How it works
- **Include:** Feature names, previous behavior/gap, motivation, audience, behavioral details
- **Avoid:** Internal jargon, implementation details, commit-level granularity

### Product Updates GTM
- **Length:** 300-600 words
- **Tone:** Clear, customer-centric, enabling for sales/marketing/CS
- **Structure:** Feature name → Value proposition → Target audience → Key messaging (3-4 bullets) → How it works → Rollout plan → Supporting assets needed
- **Include:** Customer-facing language, segment targeting, messaging pillars, asset checklist
- **Avoid:** Engineering details, internal acronyms, vague timelines, feature-only descriptions without value framing

## Guidelines

1. **Match the format exactly** — Follow the structure and length constraints for each style
2. **Adapt tone per style** — Executive emails are strategic; Slack is casual; Notion is thorough; Release notes are user-facing
3. **When generating all styles** — Output them sequentially, separated by a horizontal rule (`---`), with a header for each style (all five formats)
4. **Ground in the content** — Use real numbers, names, and context from the input. Never fabricate data.
5. **Keep the user's intent** — Don't add information that wasn't in the original content

## Example

See [examples/sample-output.md](examples/sample-output.md) for a reference example showing all four styles generated from a single input.
