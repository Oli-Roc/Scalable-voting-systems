# ⚖️ Strategic Optimization of Social Welfare (SOW)

> *A parametric family of additive scoring rules grounded in welfare economics*

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](LICENSE)
[![Welfare Metrics](https://img.shields.io/badge/Welfare_Metrics-4-purple)](#the-four-welfare-criteria)
[![Archetypes](https://img.shields.io/badge/Archetypes-9-orange)](#nine-strategic-archetypes)
[![Complexity](https://img.shields.io/badge/Complexity-O(n%2BR)-green)](#complexity)

**Author:** Olivier Rocca · Vallauris, 23 March 2026

[📄 Paper](#) · [🚀 Quick Start](#quick-start) · [📐 Framework](#the-wo-framework) · [🗳️ Applications](#applications) · [📖 Cite](#citation)

---

## Why SOW?

Every collective decision procedure implicitly optimizes for a welfare criterion. **Plurality** favors enthusiastic minorities regardless of how many find the outcome unacceptable. **Approval voting** minimizes rejection. Neither procedure makes this choice explicit, and neither provides a rigorous method for navigating between these extremes.

**SOW makes the choice explicit, auditable, and principled.**

| Audience | What SOW gives you |
| --- | --- |
| 🏢 **Organizations** | Turn an arbitrary technical choice into a governed design decision. Know which types of alternatives your rule systematically favors, before any vote is cast. |
| 🗳️ **Democratic systems** | Approval-type WO rules eliminate the spoiler effect and Duverger's coordination problem. Sincere voting becomes a Nash equilibrium. Manipulation drops from 52% to 9% under polarization. |
| 📐 **Researchers** | A complete representation theorem strictly generalizing Young (1975) to vector-valued score functions. Formal proofs of 8 axiomatic properties. Full reproducibility specs. |
| ⚡ **Engineers** | O(n+R) time, O(R) space per alternative. Exact partial aggregation across independent precincts. Optimal parallelization at k = √(n/R) nodes. |

---

## The WO Framework

A WO rule is a weighted sum over a **profile vector**. The vector encodes a welfare philosophy; the weight function ω selects the criterion.

```
Eval(π, ω)(p, a)  =  Σ_{r=1..R}  ω(r) · π_p(a)[r]
```

### Profile vectors

| Vector | Definition | Welfare signal |
| --- | --- | --- |
| `rate_p(a)[r]` | Fraction of voters who gave *a* rank *r* | Raw distribution |
| `supp_p(a)[r]` | Fraction who ranked *a* within top *r* | **Elitist** (leximax) |
| `appr_p(a)[r]` | Fraction who did not reject *a* by rank *r* | **Egalitarian** (leximin) |
| `cons_p(a)[r]` | Symmetric combination of supp and appr | **Nash / Borda** |

### Score space (necessary and sufficient)

```
s ∈ S_WO  ⟺  s(1) ≥ s(2) ≥ … ≥ s(R) ≥ s(⊥) = 0
```

> **Theorem 4.1 — Representation (complete proof)**
>
> A scoring rule F is a WO rule **if and only if** it satisfies Anonymity, Neutrality, Consistency, WO-IIA, and Monotonicity, with score function s ∈ S\_WO. The WO family is **exactly the preimage of S\_WO** under Young's (1975) score-function map — a strict generalization to vector-valued score functions.

### The four welfare criteria

| ω(r) | Criterion | Classic equivalent |
| --- | --- | --- |
| Arithmetic `R−r+1` | **Utilitarian** — maximize total utility | Borda count |
| Lexicographic on `appr` | **Egalitarian** — protect the worst-off | Leximin / Approval |
| Lexicographic on `supp` | **Elitist** — reward peak enthusiasm | Leximax / Plurality |
| Geometric `log(R−r+1)` | **Nash welfare** — multiplicative fairness | Nash bargaining |

---

## Axiomatic Properties

All 8 properties hold for every WO rule.

| Axiom | Statement |
| --- | --- |
| **WO-IIA** | Score of *a* depends only on ballots for *a* |
| **Common Scale Independence** | Rescaling all utilities by λ > 0 leaves all rankings unchanged |
| **Summability** | Partial tallies from disjoint precincts combine exactly |
| **Monotonicity** | Improving a ballot for *a* never decreases *a*'s score |
| **Resolvability** | Tie probability → 0 as n → ∞ under any non-atomic distribution |
| **Anonymity** | Permuting voters leaves all scores unchanged |
| **Neutrality** | Permuting alternatives produces the equivalent permutation of scores |
| **Consistency** | If *a* beats *b* in two disjoint sub-electorates, *a* beats *b* in their union |

---

## Nine Strategic Archetypes

Crossing three **support** tiers × three **approval** tiers yields nine canonical profiles. Built via a statistically validated fuzzy-logic protocol (10⁷ samples, σ = 0.20, seed = 42).

**Tier boundaries:** Low = [0, 0.35) · Mid = [0.35, 0.65) · High = [0.65, 1]

| | Low Support | Mid Support | High Support |
| --- | --- | --- | --- |
| **High Approval** | 🟡 **Mixed** — acceptable but not inspiring; the compromise nobody opposes | 🟢 **Viable** — competitive on both dimensions | 🟢 **Consensual** ★ — wins under every WO parameterization |
| **Mid Approval** | 🔴 **Unsatisfying** — weak on all dimensions | 🟡 **Compromise** — middle of the road | 🟢 **Performing** — deep backing, moderate resistance |
| **Low Approval** | 🔴 **Dominated** — never wins | 🔴 **Unpopular** — high rejection regardless of support | 🟡 **Polarizing** — fervent fans, strong opposition; wins only under plurality-type rules |

★ **Consensual** ranks first under all seven tested WO rule parameterizations.

> **The Mixed paradox — resolved (§7.2)**
> Low support + high approval is not contradictory. It describes an alternative ranked in the *middle* by everyone — nobody's first choice, but nobody rejects it either. Formally: `supp(a)[1] ≈ 0` and `appr(a)[R] ≈ 1`. This is the standard profile of a compromise candidate.

---

## Manipulation Resistance

> **Gibbard–Satterthwaite (1973/1975):** every non-trivial deterministic rule is manipulable for |M| ≥ 3. This is a universal impossibility — not a defect specific to WO. What varies is the *frequency* of profitable manipulation.

Simulation: n = 21 voters, m = 5 alternatives, R = 5 grades, 10 000 profiles per cell, seed = 42.

| Rule | Uniform manip% | Polarized manip% | Δ |
| --- | :---: | :---: | :---: |
| Plurality | 38.2% | 52.1% | ↑ +13.9pp |
| Borda | 29.1% | 38.7% | ↑ +9.6pp |
| Consensual geometric | 17.4% | 14.1% | ↓ −3.3pp |
| Approval | 14.7% | 9.4% | ↓ −5.3pp |
| **Nash geometric** ★ | **11.3%** | **8.9%** | ↓ **−2.4pp** |

★ Nash geometric achieves the lowest manipulation rate under both distributions.

**Key insight:** Approval-type rules become *less* manipulable under polarization — exactly when electoral integrity matters most. Plurality rules become *more* manipulable.

### Dominant strategies

**Approval-type rules:** Sincere approval is weakly dominant regardless of others' ballots. Sincere voting is always a Nash equilibrium. Duverger's coordination problem is fully eliminated (Proposition 6.2).

**Nash geometric:** For any voter *i*, the manipulation gain is bounded by `log(1 + 1/n) / log(nash(a)) → 0` as n → ∞. Faster convergence to strategy-resistance than Borda (Proposition 6.4).

---

## Quick Start

```python
from sow import WORule, Profile

# 3 voters, 3 alternatives, scale R=4
p = Profile(
    voters=[
        {'a': 1, 'b': 2, 'c': 'rej'},
        {'a': 2, 'b': 1, 'c': 3},
        {'a': 'rej', 'b': 1, 'c': 2},
    ],
    R=4
)

utilitarian = WORule(pi='support',  omega='arithmetic')    # Borda
egalitarian = WORule(pi='approval', omega='lexicographic') # Leximin
elitist     = WORule(pi='support',  omega='lexicographic') # Leximax
nash        = WORule(pi='rate',     omega='geometric')     # Nash welfare

for rule in [utilitarian, egalitarian, elitist, nash]:
    print(rule.name, rule.rank(p), rule.classify(p))
    # e.g. → Nash  [b, a, c]  Performing
```

### Ballot syntax

| Symbol | Meaning |
| --- | --- |
| `>` | Rank change |
| `~` | Equal rank |
| `?` | Intentional rank skip (ordinal, not cardinal) |
| `\|` | Support / rejection separator |
| `,` | Between rejected alternatives |

Example: `a > b > ? > c | d , e` — *a* is rank 1, *b* rank 2, *c* rank 4 (rank 3 intentionally skipped), *d* and *e* rejected.

---

## Applications

### 🏢 Corporate governance
Board decisions, R&D project selection, M&A candidate ranking. Choose the welfare criterion that matches your firm's values — utilitarian for expected-value maximization, leximin to protect dissenting stakeholders.

### 🗳️ Political elections
Approval-WO eliminates spoiler effects and vote-splitting. Nash-geometric rules are asymptotically manipulation-proof at scale. Summability enables fully auditable distributed tallying with no centralized trust.

### 🤖 AI alignment & RLHF
Aggregate annotator preferences into reward signals that explicitly optimize a welfare criterion rather than naive majority vote. Formally prevent strategically inflated scores.

### 🌐 Decentralized protocols
Summability enables exact partial aggregation in DAO governance, federated learning, or multi-region rollout decisions — no coordinator, no raw data sharing required.

### 📊 Multi-criteria prioritization
Roadmap ranking, supplier selection, policy evaluation. The archetype matrix gives an ex-ante strategic audit before any vote is cast.

---

## Out of Scope — Formal Exclusions

Three rule classes are provably outside the WO family due to structural incompatibility with WO axioms.

| Rule class | Examples | Violated axiom | Reason |
| --- | --- | --- | --- |
| Condorcet-consistent | Schulze, Ranked Pairs, Kemeny | WO-IIA | Score of *a* requires pairwise comparisons with *b*, *c*, … |
| Sequential elimination | IRV, STV, Coombs | Summability | Path-dependent elimination; partial tallies cannot be combined |
| Budget allocation | Cumulative voting | WO-IIA | Fixed budget creates cross-alternative strategic interactions |

---

## Known Limitations

- **Hybrid rule game theory:** Nash equilibrium characterization for consensual rules (Borda, geometric) remains open.
- **Gaussian preference assumption:** The archetype protocol is calibrated for Gaussian preferences. Strongly bimodal distributions may yield different classification results.
- **No real electoral validation:** All results are analytical or simulation-based. Validation against e.g. Baujard et al. (2014) would strengthen empirical claims.
- **IUC assumption:** Utilitarian and Nash rules require interpersonal utility comparability. Egalitarian and elitist criteria require only ordinal within-ballot comparability.
- **Cardinal scale required:** Theorem 4.1 applies to cardinal scales T = {1, …, R}. Extensions to continuous scales or partial orders require separate treatment.

---

## Citation

```bibtex
@article{rocca2026sow,
  title   = {Large-Scale Optimization of Social Welfare:
             A Parametric Family of Additive Scoring Rules},
  author  = {Rocca, Olivier},
  year    = {2026},
  month   = {March},
  address = {Vallauris, France},
  note    = {Preprint}
}
```

**Built on:** Young (1975) · Arrow (1951) · Gibbard (1973) · Brams & Sanver (2009) · Pivato (2013, 2014) · Balinski & Laraki (2011) · d'Aspremont & Gevers (1977)

---

*"Turn the choice of a collective decision procedure from an arbitrary technical decision into a principled strategic design problem."*
