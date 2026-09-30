---
name: repo-readme
description: Create or standardize a repository README.md using a consistent, professional structure derived from evidence in the repository. Use when creating, rewriting, refreshing, normalizing, or improving a GitHub repository README. Inspect the repository before writing and never invent project capabilities, commands, versions, deployment targets, CI status, or configuration.
---

# Repository README

Create or update the root `README.md` so repositories share a consistent, professional documentation style while preserving project-specific information.

## Source of truth

Derive the README from the repository itself.

Before writing, inspect the relevant available sources, including:

- existing `README.md`;
- package/project manifests;
- dependency and lock files;
- source tree;
- build configuration;
- test configuration;
- CI workflows;
- deployment configuration;
- environment examples;
- Docker files;
- API specifications;
- repository documentation;
- Git remote metadata when available.

Do not infer unsupported capabilities.

Do not claim that tests, CI, deployments, releases, platforms, integrations, or features exist unless repository evidence supports the claim.

Prefer exact executable commands already defined by the project.

## Preserve information

When an existing README contains useful project-specific information, retain it unless it is obsolete, duplicated, incorrect, or contradicted by the repository.

Standardize the presentation rather than deleting valuable documentation.

Do not overwrite intentionally maintained legal, security, attribution, citation, academic, licensing, or contributor information.

## README structure

Use the following order when the corresponding information exists:

1. Project heading
2. Short project description
3. Badges
4. Overview
5. Features
6. Tech Stack
7. Architecture
8. Getting Started
9. Configuration
10. Development Commands
11. Testing and Quality
12. Project Structure
13. API or Interfaces
14. Deployment
15. Contributing
16. License

Do not create empty or speculative sections.

Small repositories may omit sections that add no useful information.

## Heading

Start with:

```md
# Project Name

Short, concrete description of what the project does and who or what it is for.
```

The description should normally be one or two sentences.

Do not use marketing language unless the repository already establishes it.

## Badges

Keep badges useful and restrained.

Include a badge only when its target can be verified from the repository.

Good candidates include:

- CI workflow;
- release/version;
- license;
- runtime or framework version when authoritative;
- package publication when the package actually exists.

Do not add decorative badge walls.

Do not create badges for technologies merely because they are dependencies.

Prefer no badges over inaccurate badges.

## Overview

Explain:

- what the project is;
- the main problem it solves;
- its principal runtime or execution model;
- any essential architectural context.

Keep this section compact.

## Features

Include only meaningful user-facing or developer-facing capabilities confirmed by the repository.

Use short bullets.

Do not convert implementation details into fake product features.

## Tech Stack

Use a compact Markdown table when useful:

```md
| Area | Technology |
| --- | --- |
| Backend | ... |
| Frontend | ... |
| Database | ... |
| Testing | ... |
| Deployment | ... |
```

Include only relevant areas.

Prefer exact framework/runtime versions when they are explicitly pinned or otherwise authoritative.

## Architecture

Describe the high-level system structure rather than every file.

For a monorepo or multi-component project, identify major components and their responsibilities.

Use Mermaid only when it materially improves understanding and when GitHub-compatible Mermaid is sufficient.

Do not create architectural relationships unsupported by the codebase.

## Getting Started

Make the shortest reliable path from clone to running development environment.

Prefer:

```md
## Getting Started

### Prerequisites

...

### Installation

```bash
...
```

### Run

```bash
...
```
```

Use the package manager and tooling selected by the repository.

Do not silently substitute npm for pnpm, pip for uv, Maven for Gradle, or equivalent tooling.

## Configuration

Document environment variables only when they can be identified reliably.

Never place real credentials, secrets, tokens, passwords, private URLs, or private keys in the README.

Prefer referencing an existing `.env.example` when available.

Clearly distinguish required and optional configuration when the repository provides enough evidence.

## Development Commands

If the repository exposes several useful commands, provide a compact table:

```md
| Command | Purpose |
| --- | --- |
| `...` | ... |
```

Commands must correspond to real scripts, Make targets, task runner commands, or documented tooling.

## Testing and Quality

Document actual test, lint, formatting, type-checking, coverage, validation, or quality commands.

Do not claim that a quality gate passes merely because it exists.

A passing-status statement requires current execution evidence or an authoritative repository status.

## Project Structure

Show only the directories necessary to understand the project.

Example:

```text
.
├── apps/
├── packages/
├── docs/
└── ...
```

Do not dump the complete repository tree.

Add short inline descriptions only when useful.

## API or Interfaces

Document the canonical API specification, generated documentation, MCP interface, CLI, package API, mobile deep links, or other public interfaces when applicable.

Link to existing detailed documentation instead of duplicating large specifications.

## Deployment

Describe deployment only when deployment configuration or authoritative documentation exists.

Identify the deployment mechanism and the commands or workflow required.

Do not expose sensitive infrastructure information.

## Contributing

Keep contributing instructions short unless the repository has an established contribution process.

Link to `CONTRIBUTING.md` when present rather than duplicating it.

## License

Determine the license from the repository.

Link to the actual license file when present.

Do not assume MIT or another license.

If no license exists, omit the section unless the user explicitly asks to document the absence of a license.

## Style

Optimize for GitHub rendering.

Use:

- concise paragraphs;
- descriptive headings;
- short lists;
- fenced code blocks with language identifiers;
- relative repository links where practical;
- tables only for genuinely tabular information;
- one blank line between logical Markdown blocks.

Avoid:

- excessive emoji;
- decorative Unicode;
- unnecessary HTML;
- excessive centered content;
- huge badge collections;
- repeated information;
- generic boilerplate;
- fake roadmap items;
- promotional filler.

The result should look deliberately designed while remaining easy to maintain as plain Markdown.

## Consistency

When this skill is used across multiple repositories, preserve the same:

- section naming;
- section ordering;
- Markdown conventions;
- badge philosophy;
- command presentation;
- technical tone.

Project-specific content may differ, but the documentation system should remain recognizable.

## Validation

Before finishing:

1. compare every significant claim against repository evidence;
2. verify commands against project configuration;
3. verify referenced relative paths exist;
4. verify links that can be checked locally;
5. remove empty sections;
6. remove unsupported claims;
7. ensure Markdown structure is valid;
8. review the diff when modifying an existing README.

The final README must describe the repository that actually exists, not the repository the author may eventually want to build.
