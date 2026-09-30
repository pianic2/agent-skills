---
name: repo-readme
description: Use when creating, rewriting or improving a GitHub repository README that should be concise, visual-first and grounded in repository evidence.
---

# Repository README

Create or improve the root `README.md` as a concise GitHub landing page. Inspect the repository before writing and derive every technical claim from evidence.

## Evidence first

Inspect the existing README, manifests and lockfiles, source tree, scripts, tests, CI workflows, deployment configuration, API specifications, docs, assets, license and relevant Git metadata. Preserve useful existing information unless evidence shows it is obsolete or incorrect.

Never invent features, versions, commands, integrations, CI or release status, deployments, coverage, architecture, URLs or support claims. Verify commands against project configuration, badges against authoritative sources, and every linked file or image against the repository. Omit anything that cannot be verified; do not imply tests pass or a service is deployed without current evidence.

## Visual identity

Start with a hero image, followed by the project name, a one-line description, compact status badges and primary technology icons. Keep introductory text minimal and put Quick Start near the top.

When creating visual assets, use:

```text
docs/assets/
├── logo.svg
└── readme-hero.svg
```

`logo.svg` is the reusable project identity mark for use outside the README. Keep it distinct from `readme-hero.svg`, a wide composition made for the README. The logo expresses the project's identity; it is not an architecture or process diagram. The hero may incorporate the logo, but must not be the only form of the identity.

Give the hero one dominant idea, a strong composition and generous negative space. Use a reduced, coherent palette and deliberate typography; do not default to monospace. Prefer abstract, geometric or editorial symbols with a clear silhouette that remain recognizable at small sizes.

Avoid boxes with arrows, pipeline stages, terminals, database cylinders, robots, code brackets and generic AI branding. Keep technical architecture out of the hero and explain it later with a concise diagram, table or text when evidence supports it.

Use a consistent visual language across assets. Keep SVGs lightweight and readable. Verify that local asset paths exist and that images still work at README display size.

## Header elements

### Badges

Use a small, consistent set of compact badges (typically 2–6) for verifiable project status, such as CI, release, license or coverage. Prefer authoritative providers. Badges describe status; they are not a second technology list. Omit unavailable or unverified status.

### Technology icons

Show only a few primary technologies confirmed by repository evidence. Keep these icons visually separate from status badges and omit unsupported or unavailable icons. Do not turn transitive dependencies into an icon wall.

### Optional preview

After the header, include one representative screenshot or output only when the project has a meaningful visual result and the asset is available. Do not add decorative or fabricated previews.

## README structure

Follow this order, omitting sections that lack evidence or value for the project:

1. Hero image
2. Project name
3. One-line description
4. Badges
5. Technology icons
6. Optional visual preview
7. Quick Start
8. Architecture
9. Development
10. Testing
11. API / Interfaces
12. Deployment
13. Project Structure
14. Contributing
15. License

Use concise, scannable headings and a consistent set of heading icons where appropriate. Do not add an Overview or other filler section to repeat the one-line description. Omit empty sections.

### Quick Start

Place Quick Start close to the top, immediately after the optional preview when present. Prefer the fewest verified commands that get a developer running. Use the repository's actual tooling and scripts; never substitute familiar commands for project-specific ones.

### Architecture

Keep architecture out of the hero. Prefer a compact Mermaid diagram, image or table over prose when it clarifies real repository structure. Include only verified components and relationships; omit the section for simple projects where it adds little.

### Development and testing

Use short command tables or code blocks for verified setup, development, lint and test commands. Do not claim a check passes unless it has been run and its result is current.

### API, deployment and project structure

Document public interfaces and deployment only when evidenced by source, configuration or authoritative project documentation. Show only the important project paths, not a full tree. Link to canonical docs rather than duplicating detail.

### Contributing and license

Include these sections only when contribution guidance or a license is present and can be linked or summarized accurately.

## Concision and progressive disclosure

Favor images, concise tables, Mermaid diagrams, links and executable commands over long paragraphs. Remove marketing filler, repeated explanations, giant tables, excessive emoji and decorative markup. Keep the README focused on understanding the project, running it and finding deeper documentation. Put extended guides under `docs/` (or the repository's established documentation location) and link to them.

Do not add a table of contents automatically; use one only when a long README needs it for navigation.

## Final review

Before finishing, check that:

- all claims, commands, versions, badges and diagrams are supported by evidence;
- `logo.svg` and `readme-hero.svg` have distinct, appropriate roles and verified paths;
- images and links resolve, and the hero reads clearly at small sizes;
- the section order follows the structure above, with unsupported sections omitted;
- Quick Start is easy to reach and the README contains no repeated or unnecessary prose.
