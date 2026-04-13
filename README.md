# shopify-pagefly-migration

A [Claude Code](https://claude.com/claude-code) skill for migrating Shopify product pages off PageFly (or any third-party page builder) to native Liquid sections and JSON templates.

一个 [Claude Code](https://claude.com/claude-code) 技能，用于将 Shopify 商品页从 PageFly（或任何第三方页面构建器）迁移到原生 Liquid 分区与 JSON 模板。

[Claude Code](https://claude.com/claude-code) のスキルで、Shopify の商品ページを PageFly（または他のサードパーティページビルダー）からネイティブ Liquid セクション + JSON テンプレートへ移行します。

---

## What this skill teaches / 本技能涵盖的内容 / このスキルが教えること

### English

An end-to-end workflow for converting a builder-dependent product page into a native theme template using reusable custom sections. It covers:

- Verbatim content extraction (text + images, no fabrication)
- Measuring the original container width before implementing
- Reusing a shared custom section library across products
- Safe preview via `?view=<suffix>`
- Avoiding Shopify's schema caching pitfall
- The correct "hide source first, switch template_suffix second" order
- Post-switch verification via browser (not curl, due to CDN caching)

### 中文

端到端工作流：将依赖第三方构建器的商品页转换为使用可复用自定义分区的原生主题模板。内容包括：

- 忠实提取原始内容（文本 + 图片，不得编造）
- 实施前先测量原始容器宽度
- 在多个商品之间复用同一套自定义分区库
- 通过 `?view=<suffix>` 安全预览
- 规避 Shopify 的 schema 缓存陷阱
- 正确的「先隐藏原页、再切换 template_suffix」顺序
- 切换后通过浏览器验证（因 CDN 缓存，不要用 curl）

### 日本語

サードパーティビルダーに依存した商品ページを、再利用可能なカスタムセクションによるネイティブテーマテンプレートへ変換する、エンドツーエンドのワークフロー。内容：

- 元コンテンツの忠実抽出（テキスト + 画像、創作禁止）
- 実装前に元コンテナ幅を実測
- 複数商品で共有するカスタムセクションライブラリの再利用
- `?view=<suffix>` による安全なプレビュー
- Shopify のスキーマキャッシュ問題の回避
- 「元ページを非表示 → template_suffix 切替」の正しい順序
- 切替後はブラウザで検証（CDN キャッシュのため curl は不可）

---

## Install (Claude Code) / 安装（Claude Code）/ インストール（Claude Code）

```bash
git clone https://github.com/SDbyFrankChen/shopify-pagefly-migration-skill.git \
  ~/.claude/skills/shopify-pagefly-migration
```

### English

Claude Code picks it up automatically. Invoke it with the `Skill` tool:

```
skill: shopify-pagefly-migration
```

Or reference it in the current conversation — the skill loader discovers it by the `Use when...` description in the frontmatter.

### 中文

Claude Code 会自动识别该技能。通过 `Skill` 工具调用：

```
skill: shopify-pagefly-migration
```

或直接在对话中引用——技能加载器会根据 frontmatter 中的 `Use when...` 描述自动匹配。

### 日本語

Claude Code が自動で認識します。`Skill` ツールで呼び出せます：

```
skill: shopify-pagefly-migration
```

あるいは会話中に参照すれば、frontmatter の `Use when...` 説明を元にスキルローダーが自動検出します。

---

## Install (manual reference) / 手动参考 / 手動で参照

**English**: If you aren't using Claude Code, read [`SKILL.md`](./SKILL.md) directly. It is self-contained.

**中文**: 如果你不使用 Claude Code，直接阅读 [`SKILL.md`](./SKILL.md) 即可，它是自包含的。

**日本語**: Claude Code を使わない場合は、[`SKILL.md`](./SKILL.md) を直接読んでください。単体で完結しています。

---

## Scope / 范围 / スコープ

### English

This skill captures a repeatable workflow proven on real migrations. It does **not** include:

- Section liquid files — you bring your own section library
- Credentials or API client setup — you wire those in yourself
- Store-specific CSS — every theme is different

The skill tells you *what* to do and *why*; the specifics of your sections, theme, and store stay in your own working folder.

### 中文

本技能沉淀了经过真实迁移验证的可复用工作流。**不包含**以下内容：

- 分区 Liquid 文件——需自行准备分区库
- 凭证或 API 客户端设置——需自行配置
- 店铺专属 CSS——每套主题都不同

本技能告诉你*做什么*与*为什么*；分区、主题、店铺的具体实现保留在你自己的工作目录中。

### 日本語

本スキルは、実際の移行で検証済みの再利用可能なワークフローをまとめたものです。以下は**含まれません**：

- セクション Liquid ファイル — セクションライブラリは各自で用意
- 認証情報や API クライアント設定 — 各自で構築
- ストア固有の CSS — テーマごとに異なる

本スキルは*何をするか*と*なぜそうするか*を示します。セクション・テーマ・ストアの固有実装は、各自の作業フォルダに残してください。

---

## License

MIT — see [LICENSE](./LICENSE).
