---
name: repo-readme
description: Use when creating, rewriting or improving a GitHub repository README that should be concise, visual-first and grounded in repository evidence.
---

# Repository README

Create or improve the target repository's root `README.md` as a concise GitHub landing page. Inspect the repository first and derive every technical claim and visual choice from evidence.

## Evidence first

Inspect the existing README, manifests and lockfiles, source tree, scripts, tests, CI workflows, deployment configuration, API specifications, docs, assets, license and relevant Git metadata. Preserve useful existing information unless evidence shows it is obsolete or incorrect.

Never invent features, versions, commands, integrations, CI or release status, deployments, coverage, architecture, URLs, project colors or support claims. Verify commands against project configuration, badges against authoritative sources, and every linked file or image against the repository. Omit anything that cannot be verified; do not imply tests pass or a service is deployed without current evidence.

## Generated stack background

Use the bundled deterministic generator for the README's opening visual. The agent discovers evidence; the script draws the background:

```text
AGENT: inspect target repository → identify primary stack and any real palette
SCRIPT: download Simple Icons → generate self-contained SVG background
```

Do not invent or manually draw an equivalent SVG, icon pattern or background. Change colors, density, angle, spacing or size by rerunning the script with different options.

### Discover the stack

Identify about 3–8 primary technologies from manifests, lockfiles, framework configuration, source tree, Docker or infrastructure configuration, and authoritative project docs. Choose the technologies that define the application and runtime. Do not count transitive dependencies, minor utilities or tools merely to fill the pattern. Pass their comma-separated names with `--stack`, using supported aliases such as `python,django,postgresql,docker`, `java,springboot,postgresql,docker`, `typescript,react,expo,nodejs` or `php,laravel,mysql,docker`.

### Discover the palette

Before generation, inspect CSS variables, design tokens, Tailwind or theme config, component libraries, brand assets, an existing authoritative logo, design-system documentation and other authoritative visual assets. Resolve and pass each verifiable value using `--background`, `--foreground`, `--accent` and `--accent-2`. Do not guess missing colors; omitted options use the script's deterministic fallback values. If no real palette is available, omit all four options.

### Generate the asset

Run the bundled standard-library script from the target repository root. The default output is `docs/assets/readme-background.svg`:

```bash
python3 /path/to/repo-readme/scripts/generate_readme_background.py \
  --stack python,django,postgresql,docker \
  --output docs/assets/readme-background.svg
```

Pass the discovered palette only when evidence supports it. The script downloads SVG paths from Simple Icons, embeds them in the generated SVG and lays them out deterministically. A missing icon warns and is skipped; `--strict` makes any missing alias or icon fatal. If no icon is available, generation fails without writing a background. Never leave external icon URLs in the generated file.

Supported aliases include `python`, `django`, `postgres`, `postgresql`, `java`, `spring`, `springboot`, `spring-boot`, `react`, `react-native`, `expo`, `typescript`, `javascript`, `node`, `nodejs`, `docker`, `php`, `laravel`, `mysql`, `redis`, `vite`, `wagtail` and `github-actions`. See `scripts/generate_readme_background.py` for accepted options and defaults.

The background is a decorative field of real stack icons: a full or softly graded color field, optional subtle glow, several staggered rows, repeated icons, low opacity and a diagonal rotation. Keep it legible and restrained. It contains icons only: no technology labels, boxes, arrows, pipelines, architecture diagrams, terminals, database cylinders, robots or generic AI motifs. Architecture belongs later in the README.

Do not automatically create `logo.svg` or another logo. Reuse an existing authoritative logo when useful. Create a new logo only when the user explicitly requests one; a generated stack background and clean text title are sufficient.

## README header and structure

Start the README with the generated background using this markup, updating the path only if a different output was intentionally selected:

```html
<p align="center">
  <img
    src="docs/assets/readme-background.svg"
    alt="Technology stack background"
    width="100%"
  />
</p>
```

Follow it with the project name, one-line evidence-based description, compact status badges, an optional separate technology icon row, and an optional meaningful preview. The separate icon row is optional because the background already communicates the stack. Keep introductory prose minimal and place Quick Start immediately after the optional preview.

Use this order, omitting sections without evidence or value:

1. Generated background
2. Project name
3. One-line description
4. Status badges
5. Optional technology icon row
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

Use compact, consistent badges for verifiable status only; they are not a second technology list. Any separate technology icons must represent primary technologies confirmed by repository evidence. Include one available, representative preview only when the project has a meaningful visual result. Do not add an Overview or filler section that repeats the one-line description, and do not leave empty sections.

### Concise technical sections

- **Quick Start:** Put the fewest verified commands near the top. Use the repository's actual tooling and scripts.
- **Architecture:** Keep it out of the background. Prefer a concise Mermaid diagram, image or table over prose when it clarifies real structure; omit it for simple projects.
- **Development and Testing:** Use short command tables or code blocks for verified setup, development, lint and test commands. Do not claim checks pass unless run with current results.
- **API / Interfaces and Deployment:** Include only interfaces and deployment evidenced by source, configuration or authoritative docs.
- **Project Structure:** Show only important paths, not the full tree.
- **Contributing and License:** Include only when guidance or a license exists and can be linked or summarized accurately.

Favor images, concise tables, Mermaid, links and commands over long paragraphs. Link to deeper documentation instead of duplicating it; put extended guides under `docs/` or the repository's established documentation location. Add a table of contents only when a long README needs one.

## Final review

Before finishing, verify that:

- claims, commands, versions, badges, palette values and diagrams are supported by evidence;
- the background was generated by the script, is self-contained and has a valid repository-relative image path;
- status badges are verifiable, and optional technology icons reflect actual primary technologies;
- every referenced file and image exists and links resolve;
- the README follows the section order, omits unsupported sections and keeps Quick Start easy to reach;
- repeated, verbose or marketing prose has been removed.
