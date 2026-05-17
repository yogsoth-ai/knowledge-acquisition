# Integration Test Scenarios

Live integration tests for the knowledge-acquisition skill repo. Run these scenarios to verify end-to-end campaign routing and execution.

## Prerequisites

- All MCP servers running (brave-search, apify, alphaxiv, semantic-scholar)
- Sibling repos available (web-browsing, literature-engine, subagent-spawning, context-management)
- Subagent support enabled
- North-star-crystallization complete (research intent crystallized)

---

## Scenario 1: Literature Survey Routing

**Prompt:**
```
/knowledge-acquisition I need a comprehensive literature review of protein language models — what methods exist, key papers, and open problems.
```

**Expected behavior:**
- Routes to `literature-survey` campaign (文献调研, 综述, 论文搜索)
- Campaign selects `scoping-survey` strategy (new field, landscape mapping)
- State Ledger printed before each iteration
- Budget enforcement active

**Quality checks:**
- [ ] Correct campaign selected (literature-survey, not baseline-establishment)
- [ ] Strategy routing within campaign works
- [ ] State Ledger printed at least 3 times
- [ ] Context-checkpoint called after strategy completion

---

## Scenario 2: Patent Mining Routing

**Prompt:**
```
/knowledge-acquisition I need to understand the patent landscape for CRISPR-based gene editing therapeutics. Who owns what, where are the white spaces?
```

**Expected behavior:**
- Routes to `patent-mining` campaign (专利分析, prior art, 白空间)
- Campaign selects `landscape-survey` strategy (broad patent landscape)
- Uses patent-specific SOPs (patent-query-formulation, classification-navigation)
- Produces landscape map with assignee analysis

**Quality checks:**
- [ ] Correct campaign selected (patent-mining)
- [ ] Patent-specific tactics invoked (not generic literature search)
- [ ] Budget targets within ±10%
- [ ] Output contains assignee/competitive intelligence data

---

## Scenario 3: Benchmark Archaeology Routing

**Prompt:**
```
/knowledge-acquisition Is the MMLU benchmark still meaningful? I suspect it's saturated and possibly contaminated.
```

**Expected behavior:**
- Routes to `benchmark-archaeology` campaign (benchmark 分析, 饱和度)
- Could route to `saturation-analysis` or `benchmark-audit` strategy
- Uses contamination-audit SOP
- Produces risk assessment with evidence

**Quality checks:**
- [ ] Correct campaign selected (benchmark-archaeology)
- [ ] Saturation signals analyzed (score trajectories)
- [ ] Contamination vectors assessed
- [ ] Output includes risk classification (critical/high/medium/low/minimal)

---

## Scenario 4: Meta-Analysis Routing

**Prompt:**
```
/knowledge-acquisition I want to synthesize all studies comparing retrieval-augmented generation to fine-tuning for domain adaptation. What's the overall effect size?
```

**Expected behavior:**
- Routes to `meta-analysis` campaign (跨研究统计综合, 效应量)
- Campaign selects `pairwise-synthesis` strategy (two-method comparison)
- Uses PICO formulation SOP
- Produces effect size estimates with heterogeneity analysis

**Quality checks:**
- [ ] Correct campaign selected (meta-analysis)
- [ ] PICO framework applied (Population, Intervention, Comparison, Outcome)
- [ ] Effect sizes extracted from multiple studies
- [ ] Heterogeneity assessed (I², Q statistic)
- [ ] Publication bias checked

---

## Scenario 5: Baseline Establishment Routing

**Prompt:**
```
/knowledge-acquisition What's the current SOTA for protein structure prediction? I need a complete performance comparison across all methods and datasets.
```

**Expected behavior:**
- Routes to `baseline-establishment` campaign (SOTA 整理, 性能对比)
- Campaign selects `method-inventory` strategy first (find all methods)
- Then `performance-extraction` (collect scores)
- Produces standardized comparison table

**Quality checks:**
- [ ] Correct campaign selected (baseline-establishment)
- [ ] Method inventory comprehensive (not just top-3)
- [ ] Conditions standardized across papers
- [ ] Output includes comparison table with provenance
- [ ] Progress curve data present

---

## Scenario 6: Multi-Campaign Composition

**Prompt:**
```
/knowledge-acquisition I'm entering the field of AI-driven protein design. I need: (1) a literature survey of the field, (2) the current SOTA baselines, and (3) an audit of the benchmarks used to evaluate these methods.
```

**Expected behavior:**
- Recognizes multi-campaign request
- Orchestrates: literature-survey → baseline-establishment ∥ benchmark-archaeology
- Each campaign executes with its own budget and state
- Final synthesis combines findings

**Quality checks:**
- [ ] Multiple campaigns invoked (not just one)
- [ ] Each campaign produces independent output
- [ ] Cross-campaign synthesis attempted
- [ ] No budget confusion between campaigns

---

## Scenario 7: Ambiguous Intent (Routing Failure)

**Prompt:**
```
/knowledge-acquisition transformers
```

**Expected behavior:**
- Cannot determine which campaign to route to
- Falls back to clarification (asks user for more context)
- Does NOT randomly pick a campaign

**Quality checks:**
- [ ] Does not blindly route to a campaign
- [ ] Asks clarifying question about research intent
- [ ] Routes correctly after clarification
