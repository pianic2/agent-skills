<h1 align="center">
  <img
    src="docs/assets/readme-background.svg"
    alt="Agent Skills — Reusable skills for repository documentation"
    width="100%"
  />
</h1>

<p align="center">
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"></a>
  <a href="#quick-start"><img src="https://img.shields.io/badge/Quick_Start-Choose_a_skill-4A5568?style=for-the-badge" alt="Quick Start"></a>
  <a href="#background-generator"><img src="https://img.shields.io/badge/Background_Generator-Python-4A5568?style=for-the-badge" alt="Background generator"></a>
</p>

Reusable agent skills for creating clear, evidence-based repository documentation.

## Quick Start

Choose a guide for the task:

- [repo-readme](skills/repo-readme/SKILL.md) creates or improves a concise repository README and includes a titled stack-background generator.
- [repo-docs](skills/repo-docs/SKILL.md) audits and organizes Markdown documentation while preserving useful content and links.

## Background Generator

The `repo-readme` skill includes a Python standard-library script that downloads Simple Icons and embeds them in a self-contained SVG. From the repository root, run:

```bash
python3 skills/repo-readme/scripts/generate_readme_background.py \
  --title "Agent Skills" \
  --subtitle "Reusable skills for repository documentation" \
  --stack python \
  --output docs/assets/readme-background.svg
```

See the [generator source](skills/repo-readme/scripts/generate_readme_background.py) for options, including dimensions and colors.

## Repository Structure

```text
.
├── skills/
│   ├── repo-docs/
│   │   └── SKILL.md
│   └── repo-readme/
│       ├── SKILL.md
│       └── scripts/
│           └── generate_readme_background.py
└── README.md
```
