<div align="center">
⚖️ Strategic Optimization of Social Welfare
A parametric family of additive scoring rules grounded in welfare economics
Afficher l'image
Afficher l'image
Afficher l'image
Afficher l'image
Afficher l'image
Vallauris, 23 March 2026 · Olivier Rocca
📄 Read the Paper · 🚀 Quick Start · 📐 Framework · 🗳️ Applications · 📖 Cite SOW

</div>
Why SOW?
Every collective decision procedure implicitly optimizes for a welfare criterion — plurality favors enthusiastic minorities regardless of how many find the outcome unacceptable; approval voting minimizes rejection. Neither procedure makes this choice explicit, and neither provides a rigorous method for navigating between these extremes.
SOW makes the choice explicit, auditable, and principled.
AudienceWhat SOW gives you🏢 OrganizationsTurn an arbitrary technical choice into a governed design decision. Know which types of alternatives your rule systematically favors, before any vote is cast.🗳️ Democratic systemsApproval-type WO rules eliminate the spoiler effect and Duverger's coordination problem. Sincere voting becomes a Nash equilibrium. Manipulation drops from 52% → 9% under polarization.📐 ResearchersA complete representation theorem strictly generalizing Young (1975) to vector-valued score functions. Formal proofs of 8 axiomatic properties. Full reproducibility specs.⚡ EngineersO(n+R) time, O(R) space per alternative. Exact partial aggregation across independent precincts. Optimal parallelization at k = √(n/R) nodes → O(√nR) wall-clock time.

The WO Framework
A WO rule is a weighted sum over a profile vector. The vector encodes a welfare philosophy; the weight function ω selects the criterion.
Eval(π, ω)(p, a)  =  Σ_{r=1..R}  ω(r) · π_p(a)[r]
Profile vectors
VectorFormulaWelfare signalrate_p(a)[r]fraction of voters who gave a rank rRaw distributionsupp_p(a)[r]fraction who ranked a within top rElitist (leximax)appr_p(a)[r]fraction who did not reject a by rank rEgalitarian (leximin)cons_p(a)[r]symmetric combination of supp and apprNash / Borda
Score space (necessary and sufficient)
s ∈ S_WO  ⟺  s(1) ≥ s(2) ≥ … ≥ s(R) ≥ s(⊥) = 0

Theorem 4.1 (Representation — complete proof)
A scoring rule F is a WO rule if and only if it satisfies Anonymity, Neutrality, Consistency, WO-IIA, and Monotonicity, with score function s ∈ S_WO.
The WO family is exactly the preimage of S_WO under Young's (1975) score-function map — a strict generalization to vector-valued score functions.

The four canonical welfare criteria
ω(r)Welfare criterionClassic equivalentArithmetic R−r+1Utilitarian — maximize total utilityBorda countLexicographic on apprEgalitarian — protect the worst-offLeximin / ApprovalLexicographic on suppElitist — reward peak enthusiasmLeximax / PluralityGeometric log(R−r+1)Nash welfare — multiplicative fairnessNash bargaining

Axiomatic Properties
All 8 properties hold for every WO rule:
#AxiomStatement1WO-IIAScore of a depends only on ballots for a2CSICommon Scale Independence — rescaling utilities by λ > 0 leaves all rankings unchanged3SummabilityPartial tallies from disjoint precincts combine exactly — enables auditable distributed deployment4MonotonicityImproving a ballot for a never decreases a's score5ResolvabilityTie probability → 0 as n → ∞ under any non-atomic distribution (CLT)6AnonymityPermuting voters leaves all scores unchanged7NeutralityPermuting alternatives produces the equivalent permutation of scores8ConsistencyIf a beats b in two disjoint sub-electorates, a beats b in their union

Nine Strategic Archetypes
Cross-tabulating support (depth of enthusiasm) × approval (breadth of acceptance) yields nine canonical profiles. Built via a statistically validated fuzzy-logic protocol (10⁷ samples, Gaussian σ=0.20, seed=42).
                 Low Support      Mid Support      High Support
               ┌────────────────┬────────────────┬────────────────┐
High Approval  │   🟡 Mixed     │   🟢 Viable    │  🟢 Consensual │
               │  "acceptable,  │ "competitive   │   "wins under  │
               │  not inspiring"│  broadly"      │   every rule"  │
               ├────────────────┼────────────────┼────────────────┤
Mid Approval   │  🔴 Unsatisfy. │  🟡 Compromise │  🟢 Performing │
               │  "weak on all  │ "middle of the │  "deep backing,│
               │   dimensions"  │    road"       │ some resistance│
               ├────────────────┼────────────────┼────────────────┤
Low Approval   │  🔴 Dominated  │  🔴 Unpopular  │  🟡 Polarizing │
               │  "never wins"  │ "high rejection│  "wins only    │
               │                │  regardless"   │  under plurali.│
               └────────────────┴────────────────┴────────────────┘
Tiers: Low = [0, 0.35)  ·  Mid = [0.35, 0.65)  ·  High = [0.65, 1]

★ Consensual ranks first under all seven tested WO rule parameterizations.
ℹ️ The Mixed paradox (resolved): Low support + high approval is not contradictory. It describes an alternative ranked in the middle by everyone — nobody's first choice, but nobody rejects it either. The classic compromise candidate. See §7.2 for formal proof.

Strategic profiles of classic rules
RuleCriterionFavorsArchetype ranking (best → worst)PluralityLeximaxHigh supportConsensual > Performing > Polarizing > …ApprovalLeximinHigh approvalConsensual ≈ Viable ≈ Mixed > …BordaUtilitarianConsensusConsensual > Performing ≈ Viable > …Nash geometricNash welfareHigh approvalConsensual > Viable > Mixed > …

Manipulation Resistance

Gibbard–Satterthwaite (1973/1975): every non-trivial deterministic rule is manipulable for |M| ≥ 3. This is a property of all voting rules, not a defect of WO. What varies is the frequency of profitable manipulation.

Simulation — n=21 voters, m=5 alternatives, R=5 grades, 10,000 profiles per cell, seed=42:
RuleUniform: manip%Polarized: manip%Δ polarizationPlurality38.2%52.1%↑ +13.9ppBorda29.1%38.7%↑ +9.6ppConsensual (geometric)17.4%14.1%↓ −3.3ppApproval14.7%9.4%↓ −5.3ppNash / geometric ★11.3%8.9%↓ −2.4pp

★ Nash geometric achieves the lowest manipulation rate under both distributions.
🔑 Key insight: Approval-type rules become less manipulable under polarization — exactly when electoral integrity matters most. Plurality rules become more manipulable.

Dominant strategies by rule class
Approval-type (leximin): Sincere approval is weakly dominant — it weakly dominates all alternative strategies regardless of others' ballots. Sincere voting is always a Nash equilibrium. Duverger's coordination problem is fully eliminated.
Nash geometric: For any voter i, the manipulation gain is bounded by:
gain_i  ≤  log(1 + 1/n) / log(nash(a))  →  0  as  n → ∞
Faster convergence to manipulation-resistance than Borda. Large electorates are asymptotically strategy-proof.
Plurality-type (leximax): Standard Duverger equilibrium — all supporters concentrate on rank 1, strategic coordination required.

Quick Start
pythonfrom sow import WORule, Profile

# 3 voters, 3 alternatives, scale R=4
p = Profile(
    voters=[
        {'a': 1, 'b': 2, 'c': 'rej'},   # voter 1
        {'a': 2, 'b': 1, 'c': 3},        # voter 2
        {'a': 'rej', 'b': 1, 'c': 2},    # voter 3
    ],
    R=4
)

# Four canonical welfare criteria
utilitarian = WORule(pi='support',  omega='arithmetic')    # Borda / utilitarian
egalitarian = WORule(pi='approval', omega='lexicographic') # leximin / egalitarian
elitist     = WORule(pi='support',  omega='lexicographic') # leximax / elitist
nash        = WORule(pi='rate',     omega='geometric')     # Nash welfare

for rule in [utilitarian, egalitarian, elitist, nash]:
    ranking  = rule.rank(p)
    archetype = rule.classify(p)  # → 'Consensual' | 'Polarizing' | ...
    print(rule.name, ranking, archetype)
WO ballot syntax
a > b > ? > c | d , e
│   │   │   │   │
│   │   │   │   └─ rejected alternatives (unranked)
│   │   │   └───── support/rejection separator
│   │   └─────────── intentional rank skip (ordinal, not cardinal)
│   └─────────────── rank change
└─────────────────── rank 1 (highest welfare)

~ denotes equal rank:   a > b ~ c | d

Applications
<table>
<tr>
<td width="50%">
🏢 Corporate Governance
Board decisions, R&D project selection, M&A candidate ranking. Choose the welfare criterion that matches your firm's values — utilitarian for expected-value maximization, leximin to protect dissenting stakeholders.
</td>
<td width="50%">
🗳️ Political Elections
Approval-WO eliminates spoiler effects and vote-splitting. Nash-geometric rules are asymptotically manipulation-proof at scale. Summability enables fully auditable distributed tallying.
</td>
</tr>
<tr>
<td>
🤖 AI Alignment & RLHF
Aggregate annotator preferences into reward signals that explicitly optimize a welfare criterion rather than naive majority vote. Formally avoid eliciting strategically inflated scores.
</td>
<td>
🌐 Decentralized Protocols
Summability enables exact partial aggregation in DAO governance, federated learning, or multi-region rollout decisions — no coordinator, no raw data sharing required.
</td>
</tr>
<tr>
<td>
📊 Multi-criteria Prioritization
Roadmap ranking, supplier selection, policy evaluation. The archetype matrix gives an ex-ante strategic audit before any vote is cast.
</td>
<td>
🎓 Social Choice Education
A unified framework bridging Social Choice Theory, Welfare Economics, and Multi-objective Optimization — showing the three traditions were never meant to be separate.
</td>
</tr>
</table>

Out of Scope (Formal Exclusions)
Three rule classes are provably outside the WO family. These are structural incompatibilities, not practical limitations:
Rule classExample rulesViolated axiomWhyCondorcet-consistentSchulze, Ranked Pairs, KemenyWO-IIAScore of a requires pairwise comparisons with b, c, …Sequential eliminationIRV, STV, Coombs, BaldwinSummabilityPath-dependent elimination; partial tallies cannot be combinedBudget allocationCumulative votingWO-IIAFixed budget creates cross-alternative strategic interactions

Known Limitations

Strategic analysis is qualitative for hybrid rules — Nash equilibrium characterization for consensual (Borda, geometric) rules remains open; the full game tree grows exponentially.
Gaussian preference assumption — the archetype protocol is calibrated for Gaussian preferences. Highly bimodal or asymmetric real-world distributions may yield different classification results.
No empirical validation on real electoral data — all results are analytical or simulation-based. Validation against e.g. the 2012 French presidential evaluative voting experiment (Baujard et al., 2014) would strengthen empirical claims.
IUC assumption — utilitarian and Nash rules require interpersonal utility comparability. In heterogeneous real-world contexts, this may not hold. Egalitarian and elitist criteria require only ordinal within-ballot comparability and remain valid regardless.
Cardinal scale required — Theorem 4.1 applies to cardinal scales T = {1, …, R}. Extensions to continuous scales or partial preference orders require separate treatment.


Citation
bibtex@article{rocca2026sow,
  title   = {Large-Scale Optimization of Social Welfare:
             A Parametric Family of Additive Scoring Rules},
  author  = {Rocca, Olivier},
  year    = {2026},
  month   = {March},
  address = {Vallauris, France},
  note    = {Preprint}
}
Built on: Young (1975) · Arrow (1951) · Gibbard (1973) · Brams & Sanver (2009) · Pivato (2013, 2014) · Balinski & Laraki (2011) · d'Aspremont & Gevers (1977)

<div align="center">
Released under the MIT License · Contributions welcome
"Turn the choice of a collective decision procedure from an arbitrary technical decision into a principled strategic design problem."
</div>
