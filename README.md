# Strict Evidence Guard

An always-on plugin and global rule (`AGENTS.md`) for **Antigravity** (and compatible AI coding/research agents such as Codex CLI, Claude Code, and Cursor) that enforces **primary-source verification** before adding data, citations, technical claims, or manuscript edits.

---

## Why This Exists / 设计初衷

When AI assistants draft scientific reviews, audit data tables, or cross-check literature, the most dangerous failure modes are silent hallucinations and subtle extrapolations:

- Citing numbers from memory or abstracts without inspecting full-text tables, footnotes, units, or control columns.
- Claiming a paper *"lacks X"* or *"does not exist"* based on a narrow keyword search or a single database.
- Treating overlapping error bars (`± SD` / `SE`) as positive trends, or converting model fitting parameters into physical measurements.
- Auditing outdated local drafts instead of the latest version.

**Strict Evidence Guard** turns primary-source discipline into an always-on cross-conversation rule.

---

## Core Rules (v1.1.0)

1. **Read Primary Sources in Full Context** — Inspect full papers, data tables (including auxiliary columns, footnotes, units, and controls), figure axes/captions, or raw local files/logs before stating technical facts or adopting/rebutting third-party/AI critiques.
2. **Verify Negative Claims Thoroughly** — Check full-text sections, alternative terminology/symbols, and supplementary records before claiming absence or non-existence.
3. **Check Uncertainties, Confounders & Author Scope** — Inspect `± SD`/`SE`, batch/sample identity, baseline controls, and incidental residues; never rewrite author-verified overlapping values as a positive difference.
4. **Separate Direct Measurements, Model Fits & Derived Math** — Distinguish directly reported observations from model parameters, extrapolations across mismatched phases/forms, and derived ratios/conversions/graph-read estimates (stating formulas and inputs).
5. **Confirm Current Version & Provide Verifiable Anchors** — Verify the latest file/draft timestamp first and anchor every added datum or claim to its exact source (`author/year`, `section/table/figure/page`, or `file path/line`); report gaps explicitly rather than filling them.

*(Casual conversation is excluded from citation formatting overhead.)*

---

## Installation / 安装方式

### Antigravity (Global Always-On Plugin)

Clone this repository directly into your global Antigravity plugins directory:

```bash
git clone https://github.com/MitsuriKanroji1228/strict-evidence-guard.git ~/.gemini/config/plugins/strict-evidence-guard
```

Verify in **Customizations** that `Strict Evidence Guard` is enabled (`rules/AGENTS.md` loads automatically across all conversations).

### Other Agents (Codex CLI / Claude Code / Cursor / Workspace Rules)

Copy `rules/AGENTS.md` into your global or project rule file (e.g., `AGENTS.md`, `CLAUDE.md`, or `.agents/rules/`).

---

## Repository Structure

```text
strict-evidence-guard/
├── plugin.json        # Antigravity plugin manifest
├── rules/
│   └── AGENTS.md      # Always-on primary-source evidence rule (v1.1.0)
├── README.md
├── LICENSE
└── .gitignore
```

## License

MIT License
