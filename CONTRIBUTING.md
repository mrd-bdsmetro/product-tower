# Contributing to Product Tower

Thanks for your interest! Here's how to contribute.

## Quick Guidelines

1. **Follow the template** — Every SKILL.md must have: frontmatter, VAI TRÒ, QUICK REFERENCE, tier sections, CANVAS, INITIALIZATION, ANTI-PATTERNS, CONSTRAINTS, HANDOFF
2. **3 examples per skill** — `bds_metro`, `saas_b2b`, `fnb_local` (consistent across all skills)
3. **Resources referenced** — Every `resources/xxx.md` must be called from SKILL.md via `📚 Đọc chi tiết: resources/xxx.md`
4. **Keep SKILL.md < 500 lines** — Move detail to `resources/`

## Adding a New Sub-Skill

1. Create folder: `skill-name/`
2. Add `SKILL.md` with proper frontmatter
3. Add `resources/` and `examples/` folders
4. Add 3 examples (bds_metro, saas_b2b, fnb_local)
5. Update root `README.md` table
6. Add handoff references in adjacent skills

## Submitting Changes

1. Fork the repo
2. Create a branch: `fix/description` or `feat/description`
3. Submit a PR with clear description
