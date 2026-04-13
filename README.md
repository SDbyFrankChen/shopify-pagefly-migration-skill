# shopify-pagefly-migration

A [Claude Code](https://claude.com/claude-code) skill for migrating Shopify product pages off PageFly (or any third-party page builder) to native Liquid sections and JSON templates.

## What this skill teaches

An end-to-end workflow for converting a builder-dependent product page into a native theme template using reusable custom sections. It covers:

- Verbatim content extraction (text + images, no fabrication)
- Measuring the original container width before implementing
- Reusing a shared custom section library across products
- Safe preview via `?view=<suffix>`
- Avoiding Shopify's schema caching pitfall
- The correct "hide source first, switch template_suffix second" order
- Post-switch verification via browser (not curl, due to CDN caching)

## Install (Claude Code)

```bash
git clone https://github.com/SDbyFrankChen/shopify-pagefly-migration-skill.git \
  ~/.claude/skills/shopify-pagefly-migration
```

Claude Code picks it up automatically. Invoke it with the `Skill` tool:

```
skill: shopify-pagefly-migration
```

Or reference it in the current conversation — the skill loader discovers it by the `Use when...` description in the frontmatter.

## Install (manual reference)

If you aren't using Claude Code, read [`SKILL.md`](./SKILL.md) directly. It is self-contained.

## Scope

This skill captures a repeatable workflow proven on real migrations. It does **not** include:

- Section liquid files — you bring your own section library
- Credentials or API client setup — you wire those in yourself
- Store-specific CSS — every theme is different

The skill tells you *what* to do and *why*; the specifics of your sections, theme, and store stay in your own working folder.

## License

MIT — see [LICENSE](./LICENSE).
