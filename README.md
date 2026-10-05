# Agent Skills

Reusable agent skills for creating and maintaining clear, evidence-based repository documentation.

## Overview

This repository contains two skills: `repo-readme` improves a repository’s root README, while `repo-docs` audits and organizes its documentation. Both derive content from repository evidence and preserve useful project-specific information.

## Available Skills

| Skill | Purpose |
| --- | --- |
| [repo-readme](skills/repo-readme/SKILL.md) | Create or improve a concise GitHub README grounded in repository evidence. Includes a script for generating a self-contained stack background SVG. |
| [repo-docs](skills/repo-docs/SKILL.md) | Audit and organize Markdown documentation while preserving content, links, and evidence. |

## Repository Structure

```text
.
├── skills/
│   ├── repo-readme/
│   │   ├── SKILL.md
│   │   └── scripts/
│   │       └── generate_readme_background.py
│   └── repo-docs/
│       └── SKILL.md
```

The README background generator uses Python standard-library modules and downloads icon SVGs from Simple Icons when run.
