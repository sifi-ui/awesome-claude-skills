# CLAUDE.md

## About This Repo

A curated list of Claude Skills. `README.md` is the product: a categorized index of skills, most of them links to external repositories. A smaller set of skills is vendored here as folders. There is no build, test suite, or package manifest.

## Layout

- `README.md` - the index. Skill listings live between the `## Skills` and `## Getting Started` headings.
- `CONTRIBUTING.md` - skill requirements, the `SKILL.md` template, and PR conventions. Read it before adding a skill.
- `<skill-name>/SKILL.md` - one folder per vendored skill at the repo root (lowercase, hyphenated). Some carry `scripts/`, `reference/`, `examples/`, or `templates/`.
- `template-skill/` - minimal starting point for a new skill.
- `document-skills/{docx,pdf,pptx,xlsx}/` - nested document skills; no `SKILL.md` at the `document-skills/` level.
- `composio-skills/<app>-automation/SKILL.md` - 832 generated app-automation skills that all follow one shape (frontmatter with `requires: mcp: [rube]`).
- `connect-apps-plugin/` - a Claude Code plugin (`.claude-plugin/`, `commands/setup.md`), not a skill.
- `.github/workflows/label-ready-skill.yml` - labels PRs that are clean README-only listings.

## Conventions

- Every `SKILL.md` starts with YAML frontmatter containing `name` (matching the folder name) and `description` (what it does and when to use it).
- README bullets use the format `- [Skill Name](url) - One-sentence description.`, with no emojis, placed alphabetically within the category.
- Commit and PR titles for new skills: `Add [Skill Name] skill`.

## Adding a README Listing

The labelling workflow only passes a PR when all of these hold:

- `README.md` is the only changed file.
- All edits fall between `## Skills` and `## Getting Started`.
- Each new bullet links to an external `https://` URL (not `composio.dev` or `anthropic.com`).
- Each new bullet sits alphabetically between its neighbours in its category.
- No crypto/web3/blockchain/NFT/token/wallet terms appear in the added lines.

Do not rename or move the `## Skills` or `## Getting Started` headings; the workflow locates the section by them.

## Notes

- The "App Automation via Composio" section of the README links to `./<app>-automation/`, but those folders live under `composio-skills/`. Mention this rather than mass-fixing links unless asked.
- Skill folders contain large vendored assets (fonts in `canvas-design/canvas-fonts/`, OOXML schemas under `document-skills/*/ooxml/`). Don't read or reformat them.
