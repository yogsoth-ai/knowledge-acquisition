<!-- markdownlint-disable -->
<div align="center">

> *Knowledge is not gathered — it is systematically excavated. The difference between reading papers and acquiring knowledge is the same as between tourism and cartography.*

</div>

# 🧠 Knowledge Acquisition

*Systematic Research Knowledge Acquisition Engine for Academic Research*

Knowledge Acquisition is not a literature search tool. It is a complete research intelligence pipeline. You provide a research intent — it surveys literature, mines patents, audits benchmarks, synthesizes cross-study evidence, and establishes SOTA baselines. Five autonomous campaigns, each a self-contained research activity domain with quantitative budget enforcement.

---

## ⚡ What It Does

- 📚 **Literature Survey** — autonomous literature survey across 5 paradigms (scoping, systematic, deep, narrative, snowball). Searches, screens, reads, categorizes, identifies gaps
- ⚖️ **Patent Mining** — patent landscape analysis with prior art search, claim decomposition, competitive intelligence, white-space mapping, and trend tracking
- 🏋️ **Benchmark Archaeology** — systematic excavation of AI/ML evaluation methodology. Audits benchmark quality, detects saturation, probes construct validity, maps coverage gaps
- 📊 **Meta-Analysis** — cross-study statistical synthesis with effect size extraction, heterogeneity investigation, publication bias detection, and GRADE evidence assessment
- 🎯 **Baseline Establishment** — SOTA performance baseline collection. Method inventory, performance extraction, condition standardization, discrepancy analysis, progress quantification

---

## 🎯 Design Philosophy

### 🎖️ Campaign-Based Architecture

Each campaign is a self-contained research activity domain. The entry point routes to the correct campaign based on user intent, then the campaign autonomously selects strategies and executes with quantitative budget enforcement.

### 📐 Four-Level Hierarchy

```bash
ENTRY.md (root)
  → Campaign (5): self-contained research activity domain
    → Strategy: selected by analysis purpose/intent
      → Tactic: multi-step orchestration pattern (reusable across strategies)
        → SOP: single operation (import or subagent)
```

### 📏 Budget Enforcement

Every strategy embeds quantitative floors using domain-natural units (papers read, patents analyzed, benchmarks audited, effect sizes extracted). State Ledgers track progress. Budget gates prevent premature exit.

---

## 🏗️ Architecture

```bash
┌───────────────────────────────────────────────────────────────┐
│  ENTRY POINT (ENTRY.md)                                       │
│  Routes to campaign based on research intent                  │
├───────────────────────────────────────────────────────────────┤
│  CAMPAIGN (5)                                                 │
│  literature-survey, patent-mining, benchmark-archaeology,     │
│  meta-analysis, baseline-establishment                        │
├───────────────────────────────────────────────────────────────┤
│  STRATEGY (25)                                                │
│  5 per campaign, selected by analysis purpose                 │
├───────────────────────────────────────────────────────────────┤
│  TACTIC (15)                                                  │
│  3 per campaign, multi-step orchestration patterns            │
├───────────────────────────────────────────────────────────────┤
│  SOP (55)                                                     │
│  Import (5 shared) + Subagent (~50)                           │
├───────────────────────────────────────────────────────────────┤
│  EXTERNAL SKILLS + MCP TOOLS                                  │
│  web-browsing, literature-engine, subagent-spawning,          │
│  context-management, brave-search, apify, alphaxiv,           │
│  semantic-scholar                                             │
└───────────────────────────────────────────────────────────────┘
```

### 🧩 Campaign Inventory

| Campaign | Strategies | Tactics | SOPs | Focus |
|----------|-----------|---------|------|-------|
| literature-survey | 5 | 3 | 11 | Academic paper survey (5 paradigms) |
| patent-mining | 5 | 3 | 10 | Patent landscape analysis |
| benchmark-archaeology | 5 | 3 | 9 | Benchmark quality & validity audit |
| meta-analysis | 5 | 3 | 10 | Cross-study statistical synthesis |
| baseline-establishment | 5 | 3 | 10 | SOTA performance baseline |
| **Total** | **25** | **15** | **50** | |

### 📁 Repository Structure

```bash
knowledge-acquisition/
├── ENTRY.md                          # Root entry point — campaign routing
├── skills/
│   ├── literature-survey/            # Campaign
│   ├── patent-mining/                # Campaign
│   ├── benchmark-archaeology/        # Campaign
│   ├── meta-analysis/                # Campaign
│   ├── baseline-establishment/       # Campaign
│   ├── scoping-survey/              # Strategy (literature-survey)
│   ├── systematic-survey/           # Strategy (literature-survey)
│   ├── ...                          # 95 more skill directories
│   └── web-search/                  # Import SOP (shared)
├── tests/
│   └── integration-prompt.md
└── README.md
```

All skills live flat in `skills/`. Organization is via frontmatter `used-by` field, not directory nesting.

---

## 🔌 Dependencies

| Dependency | Repository | What It Provides |
|-----------|-----------|-----------------|
| **web-browsing** | [yogsoth-ai/web-browsing](https://github.com/yogsoth-ai/web-browsing) | `web-search` + `web-research` |
| **literature-engine** | [yogsoth-ai/literature-engine](https://github.com/yogsoth-ai/literature-engine) | `paper-overview` + `paper-search` + `paper-research` |
| **subagent-spawning** | [yogsoth-ai/subagent-spawning](https://github.com/yogsoth-ai/subagent-spawning) | Subagent dispatch conventions |
| **context-management** | [yogsoth-ai/context-management](https://github.com/yogsoth-ai/context-management) | Checkpoint protocol |

### 🔧 MCP Servers Required

| Server | Purpose |
|--------|---------|
| **brave-search** | Web search API |
| **apify** | Google Scholar scraping + full page reading |
| **alphaxiv** | Paper search, content extraction, PDF queries |
| **semantic-scholar** | Paper lookup, citations, references, recommendations |

---

## 🚀 Quick Start

1. Clone:

```bash
git clone https://github.com/yogsoth-ai/knowledge-acquisition.git
```

2. Ensure sibling skill repos are available: `web-browsing`, `literature-engine`, `subagent-spawning`, `context-management`

3. Configure MCP servers (brave-search, apify, alphaxiv, semantic-scholar) in your Claude Code session.

4. Invoke:

```bash
/knowledge-acquisition I need to understand the patent landscape for protein language models
```

The engine routes to the correct campaign (patent-mining in this case) and executes autonomously.

---

## 📄 License

[Apache-2.0](LICENSE)

---

*Part of the [Yogsoth AI](https://github.com/yogsoth-ai) ecosystem. Built by [Pthahnix](https://github.com/Pthahnix).*
