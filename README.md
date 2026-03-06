# /communicate

A Claude Code skill that transforms any content into polished communication formats — Executive Email, Slack Update, Notion Document, or Release Notes.

## Installation

### Clone and Install

```bash
# Clone the repository
git clone https://github.com/101WaysToBug/communicate.git

# Import the skill into Claude Code
claude skill add /path/to/communicate
```

### Quick Install (without cloning)

```bash
claude skill add https://github.com/101WaysToBug/communicate
```

Or add it directly in your Claude Code settings under `skills`.

## Usage

```bash
claude
# Then invoke the skill:
/communicate "We shipped a new analytics dashboard with real-time metrics, 3x faster search, and fixed a CSV export bug"
```

You'll be prompted to choose a style:

1. **Executive Email** — Strategic update for leadership (3 paragraphs, business impact focused)
2. **Slack Update** — Quick team update (2-4 lines, casual, scannable)
3. **Notion Document** — Comprehensive async reference (300-600 words, fully standalone)
4. **Release Notes** — Structured release announcement (200-500 words, user-facing)
5. **All of the above** — All four styles in one output

## Examples

See [examples/sample-output.md](examples/sample-output.md) for a full example showing all four styles generated from a single input.

## Customization

Each style's format rules are defined in `references/`:

| File | Style |
| --- | --- |
| `style-executive-email.md` | Executive Email |
| `style-slack-update.md` | Slack Update |
| `style-notion-doc.md` | Notion Document |
| `style-release-notes.md` | Release Notes |

Edit these files to adjust tone, length, structure, or add new styles.

## Adding a New Style

1. Create a new `references/style-your-style.md` following the format of the existing styles (Purpose, Format Rules, Example)
2. Update `SKILL.md` to include the new style in the selection list and reference link

## License

MIT
