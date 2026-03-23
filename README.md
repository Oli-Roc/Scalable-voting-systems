<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SOW — Strategic Optimization of Social Welfare</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=JetBrains+Mono:wght@400;500&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0b0f1a;
    --bg2: #111827;
    --bg3: #1a2235;
    --border: rgba(255,255,255,0.08);
    --border2: rgba(255,255,255,0.14);
    --teal: #0dd9a0;
    --teal2: #0ab87f;
    --teal-dim: rgba(13,217,160,0.12);
    --teal-dim2: rgba(13,217,160,0.06);
    --gold: #f0b429;
    --gold-dim: rgba(240,180,41,0.12);
    --coral: #ff6b6b;
    --blue: #4a9eff;
    --purple: #9b8cff;
    --text: #f0f4ff;
    --muted: #8b95b0;
    --muted2: #5a6480;
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    min-height: 100vh;
  }

  /* NAV */
  nav {
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 2rem;
    border-bottom: 1px solid var(--border);
    background: rgba(11,15,26,0.95);
    position: sticky; top: 0; z-index: 100;
    backdrop-filter: blur(10px);
  }
  .nav-logo {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; color: var(--teal); letter-spacing: 0.1em;
  }
  .nav-links { display:flex; gap:1.5rem; }
  .nav-links a {
    font-size: 13px; color: var(--muted); text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--text); }
  .nav-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; background: var(--teal-dim); color: var(--teal);
    border: 1px solid rgba(13,217,160,0.25); border-radius: 4px;
    padding: 3px 8px;
  }

  /* HERO */
  .hero {
    padding: 5rem 2rem 4rem;
    max-width: 900px; margin: 0 auto;
    text-align: center;
  }
  .hero-label {
    display: inline-block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; letter-spacing: 0.15em; text-transform: uppercase;
    color: var(--teal); background: var(--teal-dim);
    border: 1px solid rgba(13,217,160,0.25);
    padding: 5px 14px; border-radius: 20px; margin-bottom: 1.5rem;
  }
  .hero h1 {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2.5rem, 6vw, 4.2rem);
    line-height: 1.12;
    color: var(--text);
    margin-bottom: 0.4rem;
  }
  .hero h1 em {
    font-style: italic; color: var(--teal);
  }
  .hero-sub {
    font-size: 1.05rem; color: var(--muted);
    max-width: 620px; margin: 1.2rem auto 2rem;
    line-height: 1.75;
  }
  .badges {
    display: flex; flex-wrap: wrap; gap: 0.5rem;
    justify-content: center; margin-bottom: 2.5rem;
  }
  .badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; padding: 4px 10px; border-radius: 4px;
    border: 1px solid;
  }
  .badge-teal { background: var(--teal-dim); color: var(--teal); border-color: rgba(13,217,160,0.25); }
  .badge-gold { background: var(--gold-dim); color: var(--gold); border-color: rgba(240,180,41,0.25); }
  .badge-blue { background: rgba(74,158,255,0.1); color: var(--blue); border-color: rgba(74,158,255,0.25); }
  .badge-purple { background: rgba(155,140,255,0.1); color: var(--purple); border-color: rgba(155,140,255,0.25); }
  .cta-group { display:flex; gap:0.75rem; justify-content:center; flex-wrap:wrap; }
  .btn {
    display: inline-block; text-decoration: none;
    padding: 0.65rem 1.5rem; border-radius: 8px;
    font-size: 14px; font-weight: 500; transition: all 0.2s; cursor: pointer;
  }
  .btn-primary {
    background: var(--teal); color: #0b0f1a;
  }
  .btn-primary:hover { background: #0ab87f; }
  .btn-ghost {
    background: transparent; color: var(--text);
    border: 1px solid var(--border2);
  }
  .btn-ghost:hover { background: var(--bg3); border-color: rgba(255,255,255,0.25); }

  /* METRICS STRIP */
  .metrics {
    display: flex; justify-content: center; flex-wrap: wrap; gap: 0;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    margin: 0; padding: 0;
  }
  .metric {
    padding: 1.75rem 2.5rem;
    text-align: center;
    border-right: 1px solid var(--border);
    flex: 1; min-width: 150px;
  }
  .metric:last-child { border-right: none; }
  .metric-val {
    font-family: 'DM Serif Display', serif;
    font-size: 2rem; color: var(--teal); display: block;
  }
  .metric-label { font-size: 12px; color: var(--muted); margin-top: 2px; }

  /* SECTIONS */
  section { padding: 4rem 2rem; max-width: 960px; margin: 0 auto; }
  .section-title {
    font-family: 'DM Serif Display', serif;
    font-size: 2rem; margin-bottom: 2.5rem; color: var(--text);
  }
  .section-title span { color: var(--teal); }

  /* WHY SOW */
  .pitch-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1px; background: var(--border);
    border: 1px solid var(--border); border-radius: 12px; overflow: hidden;
  }
  .pitch-card {
    background: var(--bg2);
    padding: 2rem;
  }
  .pitch-icon {
    width: 40px; height: 40px; border-radius: 10px;
    display: flex; align-items:center; justify-content:center;
    font-size: 18px; margin-bottom: 1rem;
  }
  .pitch-card h3 {
    font-size: 15px; font-weight: 600; margin-bottom: 0.6rem;
    color: var(--text);
  }
  .pitch-card p { font-size: 13.5px; color: var(--muted); line-height: 1.7; }
  .pitch-card .tag {
    display: inline-block; margin-top: 0.9rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; padding: 2px 8px; border-radius: 3px;
  }

  /* FORMULA BLOCK */
  .formula-block {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 12px; padding: 2rem 2.5rem; margin: 1.5rem 0;
  }
  .formula-block pre {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; color: var(--teal);
    overflow-x: auto; line-height: 1.9;
  }
  .formula-block .comment { color: var(--muted2); }

  /* ARCHETYPE TABLE */
  .archetype-grid {
    display: grid; grid-template-columns: 80px repeat(3,1fr);
    gap: 1px; background: var(--border);
    border: 1px solid var(--border); border-radius: 12px; overflow:hidden;
    font-size: 13px;
  }
  .arch-header {
    background: var(--bg3); padding: 0.75rem 1rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: var(--muted); text-align: center;
    text-transform: uppercase; letter-spacing: 0.08em;
  }
  .arch-row-label {
    background: var(--bg3); padding: 0.75rem 1rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: var(--muted); text-align: right;
    text-transform: uppercase; letter-spacing: 0.08em;
    display: flex; align-items: center; justify-content: flex-end;
  }
  .arch-cell {
    padding: 1rem; background: var(--bg2);
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    text-align: center; gap: 0.3rem;
    transition: background 0.2s;
  }
  .arch-cell:hover { background: var(--bg3); }
  .arch-name { font-weight: 600; font-size: 13px; }
  .arch-desc { font-size: 11px; color: var(--muted); }
  .arch-dot {
    width: 8px; height: 8px; border-radius: 50%;
    margin-bottom: 2px;
  }
  .dot-green { background: var(--teal); }
  .dot-amber { background: var(--gold); }
  .dot-red { background: var(--coral); }

  /* MANIPULATION TABLE */
  .manip-table {
    width: 100%; border-collapse: collapse; font-size: 13px;
  }
  .manip-table th {
    background: var(--bg3); padding: 0.75rem 1rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: var(--muted); font-weight: 500;
    border-bottom: 1px solid var(--border); text-align: left;
    text-transform: uppercase; letter-spacing: 0.06em;
  }
  .manip-table td {
    padding: 0.85rem 1rem;
    border-bottom: 1px solid var(--border);
    color: var(--text);
  }
  .manip-table tr:last-child td { border-bottom: none; }
  .manip-table tr:hover td { background: var(--bg3); }
  .pct { font-family: 'JetBrains Mono', monospace; font-size: 12px; }
  .pct-high { color: var(--coral); }
  .pct-mid { color: var(--gold); }
  .pct-low { color: var(--teal); }
  .winner-row td { background: rgba(13,217,160,0.04); }
  .winner-row:hover td { background: rgba(13,217,160,0.08) !important; }

  /* CODE BLOCK */
  .code-block {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 12px; overflow: hidden; margin: 1rem 0;
  }
  .code-header {
    display: flex; align-items: center; justify-content: space-between;
    padding: 0.65rem 1rem;
    border-bottom: 1px solid var(--border);
    background: var(--bg3);
  }
  .code-filename {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; color: var(--muted);
  }
  .code-lang {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; padding: 2px 6px; border-radius: 3px;
    background: var(--teal-dim); color: var(--teal);
  }
  .code-block pre {
    padding: 1.25rem 1.25rem; font-family: 'JetBrains Mono', monospace;
    font-size: 12.5px; line-height: 1.8; overflow-x: auto;
  }
  .kw { color: var(--purple); }
  .fn { color: var(--teal); }
  .str { color: var(--gold); }
  .comment { color: var(--muted2); }
  .num { color: var(--coral); }

  /* AXIOMS */
  .axiom-list { display: flex; flex-direction: column; gap: 0.75rem; }
  .axiom {
    display: flex; align-items: flex-start; gap: 1rem;
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 10px; padding: 1rem 1.25rem;
  }
  .axiom-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: var(--teal);
    background: var(--teal-dim); border: 1px solid rgba(13,217,160,0.2);
    border-radius: 4px; padding: 2px 7px; white-space: nowrap;
    flex-shrink: 0; margin-top: 2px;
  }
  .axiom-text { font-size: 14px; }
  .axiom-text strong { color: var(--text); font-weight: 600; }
  .axiom-text span { color: var(--muted); }

  /* THEOREM CALLOUT */
  .theorem {
    background: linear-gradient(135deg, rgba(13,217,160,0.06), rgba(74,158,255,0.04));
    border: 1px solid rgba(13,217,160,0.2);
    border-left: 3px solid var(--teal);
    border-radius: 0 10px 10px 0;
    padding: 1.5rem 1.75rem;
    margin: 1.5rem 0;
  }
  .theorem-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px; text-transform: uppercase;
    letter-spacing: 0.12em; color: var(--teal);
    margin-bottom: 0.5rem;
  }
  .theorem p { font-size: 14px; color: var(--muted); }
  .theorem p strong { color: var(--text); }

  /* APPLICATIONS */
  .app-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(240px,1fr));
    gap: 1rem;
  }
  .app-card {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 12px; padding: 1.5rem;
    transition: border-color 0.2s, transform 0.2s;
  }
  .app-card:hover {
    border-color: rgba(13,217,160,0.3);
    transform: translateY(-2px);
  }
  .app-card h3 { font-size: 14px; font-weight: 600; margin: 0.75rem 0 0.5rem; }
  .app-card p { font-size: 13px; color: var(--muted); line-height: 1.65; }
  .app-icon {
    font-size: 24px; display: block; margin-bottom: 0.25rem;
  }

  /* CITATION */
  .citation-box {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 12px; padding: 1.75rem;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px; color: var(--muted); line-height: 1.9;
  }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem; text-align: center;
    font-size: 12px; color: var(--muted2);
  }
  footer a { color: var(--teal); text-decoration: none; }

  /* SEPARATOR */
  .sep {
    border: none; border-top: 1px solid var(--border);
    margin: 0;
  }

  /* HIGHLIGHT ROW */
  .hl { color: var(--teal); font-weight: 600; }
  .hl-gold { color: var(--gold); }

  @media (max-width: 600px) {
    .metric { min-width: 120px; padding: 1.25rem 1rem; }
    .metric-val { font-size: 1.5rem; }
    nav { padding: 0.75rem 1rem; }
    .nav-links { display:none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">SOW / v1.0</div>
  <div class="nav-links">
    <a href="#framework">Framework</a>
    <a href="#archetypes">Archetypes</a>
    <a href="#strategy">Strategy</a>
    <a href="#applications">Applications</a>
    <a href="#citation">Cite</a>
  </div>
  <div class="nav-badge">Vallauris · 23 Mar 2026</div>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-label">welfare-optimization · social-choice · game-theory</div>
  <h1>Strategic Optimization<br>of <em>Social Welfare</em></h1>
  <p class="hero-sub">
    A parametric family of additive scoring rules that makes collective decision-making
    formally auditable, manipulation-resistant, and aligned with welfare economics —
    from board rooms to ballot boxes.
  </p>
  <div class="badges">
    <span class="badge badge-teal">arxiv · cs.GT</span>
    <span class="badge badge-gold">Young (1975) · generalization</span>
    <span class="badge badge-blue">O(n + R) · scalable</span>
    <span class="badge badge-purple">MIT License</span>
  </div>
  <div class="cta-group">
    <a href="#" class="btn btn-primary">Read the Paper</a>
    <a href="#" class="btn btn-ghost">Browse the Code</a>
    <a href="#citation" class="btn btn-ghost">Cite SOW</a>
  </div>
</div>

<!-- METRICS STRIP -->
<div class="metrics">
  <div class="metric">
    <span class="metric-val">9</span>
    <div class="metric-label">Strategic archetypes</div>
  </div>
  <div class="metric">
    <span class="metric-val">4</span>
    <div class="metric-label">Welfare metrics supported</div>
  </div>
  <div class="metric">
    <span class="metric-val">11.3%</span>
    <div class="metric-label">Nash manipulation rate</div>
  </div>
  <div class="metric">
    <span class="metric-val">O(n+R)</span>
    <div class="metric-label">Time complexity</div>
  </div>
  <div class="metric">
    <span class="metric-val">10⁷</span>
    <div class="metric-label">Simulation samples</div>
  </div>
</div>

<hr class="sep">

<!-- WHY SOW -->
<section id="why">
  <div class="section-title">Why <span>SOW</span>?</div>
  <div class="pitch-grid">

    <div class="pitch-card">
      <div class="pitch-icon" style="background:rgba(74,158,255,0.1);">🏛️</div>
      <h3>For Organizations &amp; Governance</h3>
      <p>Every voting rule implicitly optimizes for a welfare criterion — plurality favors enthusiastic minorities, approval minimizes rejection. SOW makes this choice <em>explicit and auditable</em>, turning an arbitrary technical decision into a governed design process.</p>
      <span class="tag" style="background:rgba(74,158,255,0.1);color:var(--blue);border:1px solid rgba(74,158,255,0.2);">Strategic alignment</span>
    </div>

    <div class="pitch-card">
      <div class="pitch-icon" style="background:rgba(13,217,160,0.1);">⚖️</div>
      <h3>For Democratic Systems</h3>
      <p>Approval-type WO rules eliminate the spoiler effect and Duverger's coordination problem by making <em>sincere voting a Nash equilibrium</em>. Polarized electorates see manipulation drop from 52% to 9% compared to plurality — exactly when electoral integrity matters most.</p>
      <span class="tag" style="background:rgba(13,217,160,0.1);color:var(--teal);border:1px solid rgba(13,217,160,0.2);">Electoral integrity</span>
    </div>

    <div class="pitch-card">
      <div class="pitch-icon" style="background:rgba(240,180,41,0.1);">📐</div>
      <h3>For Researchers &amp; Theorists</h3>
      <p>A complete representation theorem (Theorem 4.1) that strictly generalizes Young (1975) to vector-valued score functions. Formal proofs of 8 axiomatic properties, closed-form characterization of dominant strategies, and a statistically validated fuzzy archetype taxonomy with full reproducibility specs.</p>
      <span class="tag" style="background:rgba(240,180,41,0.1);color:var(--gold);border:1px solid rgba(240,180,41,0.2);">Axiomatic rigor</span>
    </div>

    <div class="pitch-card">
      <div class="pitch-icon" style="background:rgba(155,140,255,0.1);">⚡</div>
      <h3>For Engineers &amp; Platforms</h3>
      <p>Linear time, constant memory per alternative. <em>Exact partial aggregation</em> enables distributed deployment across independent sub-precincts with no coordination overhead. Optimal parallelization at k = √(n/R) nodes achieves O(√(nR)) wall-clock time.</p>
      <span class="tag" style="background:rgba(155,140,255,0.1);color:var(--purple);border:1px solid rgba(155,140,255,0.2);">Production-grade</span>
    </div>

  </div>
</section>

<hr class="sep">

<!-- FRAMEWORK -->
<section id="framework">
  <div class="section-title">The WO <span>Framework</span></div>

  <p style="color:var(--muted);margin-bottom:2rem;max-width:680px;">
    A WO rule is a weighted sum over a profile vector — rate, support (elitist), approval (egalitarian), or consensuality. The weight function ω selects the welfare criterion. One formula, four welfare philosophies.
  </p>

  <div class="formula-block">
    <pre>
<span class="comment">-- WO scoring rule (Def. 4.8)</span>
Eval<sub>(π, ω)</sub>(p, a)  =  Σ<sub>r=1..R</sub>  ω(r) · π<sub>p</sub>(a)[r]

<span class="comment">-- Where π is one of:</span>
rate<sub>p</sub>(a)[r]   <span class="comment">= fraction of voters who gave a rank r              (raw)</span>
supp<sub>p</sub>(a)[r]   <span class="comment">= fraction of voters who ranked a within top r       (elitist / leximax)</span>
appr<sub>p</sub>(a)[r]   <span class="comment">= fraction of voters who did not reject a by rank r  (egalitarian / leximin)</span>
cons<sub>p</sub>(a)[r]   <span class="comment">= symmetric combination of supp and appr             (Nash / Borda)</span>

<span class="comment">-- Score space constraint (necessary &amp; sufficient):</span>
s ∈ S<sub>WO</sub>  ⟺  s(1) ≥ s(2) ≥ … ≥ s(R) ≥ s(⊥) = 0
    </pre>
  </div>

  <div class="theorem">
    <div class="theorem-label">Theorem 4.1 — Representation (complete proof)</div>
    <p>A scoring rule F is a WO rule <strong>if and only if</strong> it satisfies Anonymity, Neutrality, Consistency, WO-IIA, and Monotonicity, with score function s ∈ S<sub>WO</sub>. The WO family is <strong>exactly the preimage</strong> of S<sub>WO</sub> under Young's (1975) score-function map — a strict generalization to vector-valued score functions.</p>
  </div>

  <p style="color:var(--muted);margin:1.5rem 0 1rem;font-size:14px;">Five extensibility axioms + three resilience axioms, all satisfied:</p>
  <div class="axiom-list">
    <div class="axiom">
      <span class="axiom-num">WO-IIA</span>
      <div class="axiom-text"><strong>Score independence</strong> <span>— the score of a depends only on ballots for a. Distinct from Arrow's IIA; trivially satisfied by all additive rules.</span></div>
    </div>
    <div class="axiom">
      <span class="axiom-num">CSI</span>
      <div class="axiom-text"><strong>Common Scale Independence</strong> <span>— rescaling all utilities by λ &gt; 0 leaves every ranking unchanged. Rank order is ordinal; cardinal rescaling is irrelevant (Lemma 3.1).</span></div>
    </div>
    <div class="axiom">
      <span class="axiom-num">SUM</span>
      <div class="axiom-text"><strong>Summability</strong> <span>— partial tallies from disjoint precincts combine exactly. Enables auditable distributed deployment. (Broken only by threshold filters.)</span></div>
    </div>
    <div class="axiom">
      <span class="axiom-num">MON</span>
      <div class="axiom-text"><strong>Monotonicity</strong> <span>— improving a ballot for alternative a never decreases a's score. Formally: Δscore = (ω(r) − ω(r′))/n ≥ 0 for r &lt; r′.</span></div>
    </div>
    <div class="axiom">
      <span class="axiom-num">RES</span>
      <div class="axiom-text"><strong>Resolvability</strong> <span>— under any non-atomic preference distribution, tie probability → 0 as n → ∞ (CLT). A single tie-breaking ballot always exists (constructive form).</span></div>
    </div>
  </div>
</section>

<hr class="sep">

<!-- ARCHETYPES -->
<section id="archetypes">
  <div class="section-title">Nine Strategic <span>Archetypes</span></div>
  <p style="color:var(--muted);margin-bottom:2rem;max-width:680px;">
    Cross-tabulating three support tiers × three approval tiers yields nine canonical alternative profiles. Built via a statistically validated fuzzy-logic protocol (10<sup>7</sup> samples, seed = 42, full reproducibility spec in §7.3). Use this matrix for <em>ex-ante</em> rule selection.
  </p>

  <div class="archetype-grid">
    <!-- header row -->
    <div class="arch-header">↑ Approval \ Support →</div>
    <div class="arch-header">Low Support</div>
    <div class="arch-header">Mid Support</div>
    <div class="arch-header">High Support</div>

    <!-- row: high approval -->
    <div class="arch-row-label">High Approval</div>
    <div class="arch-cell">
      <div class="arch-dot dot-amber"></div>
      <div class="arch-name">Mixed</div>
      <div class="arch-desc">Acceptable, not inspiring — the compromise candidate nobody opposes</div>
    </div>
    <div class="arch-cell">
      <div class="arch-dot dot-green"></div>
      <div class="arch-name">Viable</div>
      <div class="arch-desc">Strong breadth &amp; decent depth — competitive under most rules</div>
    </div>
    <div class="arch-cell">
      <div class="arch-dot dot-green"></div>
      <div class="arch-name" style="color:var(--teal);">Consensual ★</div>
      <div class="arch-desc">Top performer universally — wins under every WO parameterization</div>
    </div>

    <!-- row: mid approval -->
    <div class="arch-row-label">Mid Approval</div>
    <div class="arch-cell">
      <div class="arch-dot dot-red"></div>
      <div class="arch-name">Unsatisfying</div>
      <div class="arch-desc">Neither broad nor deep support</div>
    </div>
    <div class="arch-cell">
      <div class="arch-dot dot-amber"></div>
      <div class="arch-name">Compromise</div>
      <div class="arch-desc">Middle of the road in every dimension</div>
    </div>
    <div class="arch-cell">
      <div class="arch-dot dot-green"></div>
      <div class="arch-name">Performing</div>
      <div class="arch-desc">Intense backing, moderate resistance — wins under supportive rules</div>
    </div>

    <!-- row: low approval -->
    <div class="arch-row-label">Low Approval</div>
    <div class="arch-cell">
      <div class="arch-dot dot-red"></div>
      <div class="arch-name">Dominated</div>
      <div class="arch-desc">Weak everywhere — never wins</div>
    </div>
    <div class="arch-cell">
      <div class="arch-dot dot-red"></div>
      <div class="arch-name">Unpopular</div>
      <div class="arch-desc">High rejection regardless of support</div>
    </div>
    <div class="arch-cell">
      <div class="arch-dot dot-amber"></div>
      <div class="arch-name">Polarizing</div>
      <div class="arch-desc">Fervent fans, strong opposition — wins only under plurality-type rules</div>
    </div>
  </div>

  <p style="font-size:12px;color:var(--muted2);margin-top:0.75rem;">
    Tiers: Low = [0, 0.35) · Mid = [0.35, 0.65) · High = [0.65, 1]. ★ Consensual ranks first under all seven tested WO rules.
  </p>
</section>

<hr class="sep">

<!-- STRATEGY -->
<section id="strategy">
  <div class="section-title">Manipulation <span>Resistance</span></div>
  <p style="color:var(--muted);margin-bottom:2rem;max-width:680px;">
    Gibbard–Satterthwaite impossibility applies to all non-trivial deterministic rules — but the <em>frequency</em> of profitable manipulation varies dramatically. Simulation: n=21, m=5, R=5, 10,000 profiles, seed=42.
  </p>

  <div style="border:1px solid var(--border);border-radius:12px;overflow:hidden;">
    <table class="manip-table">
      <thead>
        <tr>
          <th>Rule</th>
          <th>Welfare criterion</th>
          <th>Uniform — manip%</th>
          <th>Polarized — manip%</th>
          <th>Δ polarization</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Plurality</strong></td>
          <td style="color:var(--muted)">Leximax (elitist)</td>
          <td class="pct pct-high">38.2%</td>
          <td class="pct pct-high">52.1%</td>
          <td class="pct pct-high">↑ +13.9pp</td>
        </tr>
        <tr>
          <td><strong>Borda</strong></td>
          <td style="color:var(--muted)">Utilitarian (arith.)</td>
          <td class="pct pct-mid">29.1%</td>
          <td class="pct pct-mid">38.7%</td>
          <td class="pct pct-mid">↑ +9.6pp</td>
        </tr>
        <tr>
          <td><strong>Consensual (geom.)</strong></td>
          <td style="color:var(--muted)">Nash welfare</td>
          <td class="pct pct-mid">17.4%</td>
          <td class="pct pct-mid">14.1%</td>
          <td class="pct pct-low">↓ −3.3pp</td>
        </tr>
        <tr>
          <td><strong>Approval</strong></td>
          <td style="color:var(--muted)">Leximin (egalitarian)</td>
          <td class="pct pct-low">14.7%</td>
          <td class="pct pct-low">9.4%</td>
          <td class="pct pct-low">↓ −5.3pp</td>
        </tr>
        <tr class="winner-row">
          <td><strong class="hl">Nash / geometric ★</strong></td>
          <td style="color:var(--muted)">Nash welfare (rate vec.)</td>
          <td class="pct pct-low hl">11.3%</td>
          <td class="pct pct-low hl">8.9%</td>
          <td class="pct pct-low hl">↓ −2.4pp</td>
        </tr>
      </tbody>
    </table>
  </div>
  <p style="font-size:12px;color:var(--muted2);margin-top:0.75rem;">
    ★ Nash geometric minimizes manipulation under both distributions (Proposition 6.4). Approval rules become <em>less</em> manipulable under polarization — exactly when integrity matters most.
  </p>

  <div style="margin-top:2rem;display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1rem;">
    <div class="theorem" style="margin:0;">
      <div class="theorem-label">Dominant strategy · Approval-type rules</div>
      <p><strong>Sincere approval is weakly dominant</strong> — it weakly dominates all alternative strategies regardless of others' ballots. Sincere voting is always a Nash equilibrium. Eliminates Duverger's coordination problem entirely.</p>
    </div>
    <div class="theorem" style="margin:0;border-left-color:var(--gold);background:linear-gradient(135deg,rgba(240,180,41,0.06),rgba(74,158,255,0.04));">
      <div class="theorem-label" style="color:var(--gold);">Nash bound · geometric rules</div>
      <p>For any voter i, the gain from any manipulation is bounded by <strong>log(1 + 1/n) / log(nash(a))</strong> → 0 as n → ∞. Faster convergence than Borda. Large electorates are asymptotically manipulation-proof.</p>
    </div>
  </div>
</section>

<hr class="sep">

<!-- QUICK START -->
<section id="quickstart">
  <div class="section-title">Quick <span>Start</span></div>

  <div class="code-block">
    <div class="code-header">
      <span class="code-filename">sow_example.py</span>
      <span class="code-lang">Python</span>
    </div>
    <pre>
<span class="kw">from</span> sow <span class="kw">import</span> <span class="fn">WORule</span>, Profile

<span class="comment"># 3 voters, 3 alternatives, scale R=4</span>
p = Profile(
    voters = [
        {<span class="str">'a'</span>: <span class="num">1</span>, <span class="str">'b'</span>: <span class="num">2</span>, <span class="str">'c'</span>: <span class="str">'rej'</span>},   <span class="comment"># voter 1</span>
        {<span class="str">'a'</span>: <span class="num">2</span>, <span class="str">'b'</span>: <span class="num">1</span>, <span class="str">'c'</span>: <span class="num">3</span>},         <span class="comment"># voter 2</span>
        {<span class="str">'a'</span>: <span class="str">'rej'</span>, <span class="str">'b'</span>: <span class="num">1</span>, <span class="str">'c'</span>: <span class="num">2</span>},   <span class="comment"># voter 3</span>
    ],
    R=<span class="num">4</span>
)

<span class="comment"># Four canonical welfare criteria</span>
utilitarian = <span class="fn">WORule</span>(pi=<span class="str">'support'</span>, omega=<span class="str">'arithmetic'</span>)  <span class="comment"># Borda / utilitarian</span>
egalitarian  = <span class="fn">WORule</span>(pi=<span class="str">'approval'</span>, omega=<span class="str">'lexicographic'</span>)  <span class="comment"># leximin</span>
elitist      = <span class="fn">WORule</span>(pi=<span class="str">'support'</span>,  omega=<span class="str">'lexicographic'</span>)  <span class="comment"># leximax / plurality</span>
nash         = <span class="fn">WORule</span>(pi=<span class="str">'rate'</span>,     omega=<span class="str">'geometric'</span>)     <span class="comment"># Nash welfare</span>

<span class="kw">for</span> rule <span class="kw">in</span> [utilitarian, egalitarian, elitist, nash]:
    ranking = rule.<span class="fn">rank</span>(p)
    archetype = rule.<span class="fn">classify</span>(p)  <span class="comment"># → 'Consensual' | 'Polarizing' | ...</span>
    <span class="fn">print</span>(rule.name, ranking, archetype)
    </pre>
  </div>
</section>

<hr class="sep">

<!-- APPLICATIONS -->
<section id="applications">
  <div class="section-title">Where to <span>Deploy</span></div>
  <div class="app-grid">
    <div class="app-card">
      <span class="app-icon">🏢</span>
      <h3>Corporate Governance</h3>
      <p>Board decisions, R&D project selection, M&amp;A candidate ranking. Choose the welfare criterion that matches your firm's values — utilitarian for expected-value maximization, leximin to protect dissenting stakeholders.</p>
    </div>
    <div class="app-card">
      <span class="app-icon">🗳️</span>
      <h3>Political Elections</h3>
      <p>Approval-WO eliminates spoiler effects and vote-splitting. Nash-geometric rules are asymptotically manipulation-proof at scale. Auditable distributed tallying — no centralized trust required.</p>
    </div>
    <div class="app-card">
      <span class="app-icon">🤖</span>
      <h3>AI Alignment &amp; RLHF</h3>
      <p>Aggregate annotator preferences into reward signals that explicitly optimize a welfare criterion rather than naive majority vote. Avoid eliciting strategically inflated scores.</p>
    </div>
    <div class="app-card">
      <span class="app-icon">🌐</span>
      <h3>Decentralized Protocols</h3>
      <p>Summability enables exact partial aggregation in DAO governance, federated learning aggregation, or multi-region rollout decisions — no coordinator, no data sharing required.</p>
    </div>
    <div class="app-card">
      <span class="app-icon">📊</span>
      <h3>Multi-criteria Prioritization</h3>
      <p>Roadmap ranking, supplier selection, policy evaluation. The archetype matrix gives an ex-ante strategic audit: before any vote, know which types of options your rule systematically favors.</p>
    </div>
    <div class="app-card">
      <span class="app-icon">🎓</span>
      <h3>Social Choice Education</h3>
      <p>A unified framework bridging Social Choice Theory, Welfare Economics, and Multi-objective Optimization. The three traditions were never designed to be separate — SOW shows they needn't be.</p>
    </div>
  </div>
</section>

<hr class="sep">

<!-- LIMITS -->
<section id="limits">
  <div class="section-title">Known <span>Limits</span></div>
  <p style="color:var(--muted);margin-bottom:1.5rem;max-width:680px;font-size:14px;">
    Three classes of rules are provably outside the WO family. These are structural exclusions — incompatibility with WO axioms, not practical difficulty.
  </p>
  <div class="axiom-list">
    <div class="axiom">
      <span class="axiom-num">OUT-1</span>
      <div class="axiom-text"><strong>Condorcet-consistent rules</strong> <span>(Schulze, Ranked Pairs, Kemeny) — require pairwise majority comparisons, violating WO-IIA. The score of a cannot depend only on ballots for a when pairwise defeats are needed.</span></div>
    </div>
    <div class="axiom">
      <span class="axiom-num">OUT-2</span>
      <div class="axiom-text"><strong>Sequential elimination rules</strong> <span>(IRV, STV, Coombs) — path-dependent elimination is incompatible with Summability. Two precincts cannot combine partial IRV tallies exactly.</span></div>
    </div>
    <div class="axiom">
      <span class="axiom-num">OUT-3</span>
      <div class="axiom-text"><strong>Budget allocation rules</strong> <span>(Cumulative voting) — fixed budget constraints create game-theoretic interactions across alternatives, violating WO-IIA. The WO ballot's skip symbol ? provides analogous expressivity without the strategic vulnerability.</span></div>
    </div>
  </div>
</section>

<hr class="sep">

<!-- CITATION -->
<section id="citation">
  <div class="section-title">Cite <span>SOW</span></div>
  <div class="citation-box">
@article{rocca2026sow,<br>
&nbsp;&nbsp;title   = {Large-Scale Optimization of Social Welfare:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A Parametric Family of Additive Scoring Rules},<br>
&nbsp;&nbsp;author  = {Rocca, Olivier},<br>
&nbsp;&nbsp;year    = {2026},<br>
&nbsp;&nbsp;month   = {March},<br>
&nbsp;&nbsp;address = {Vallauris, France},<br>
&nbsp;&nbsp;note    = {Preprint}<br>
}
  </div>
  <p style="font-size:13px;color:var(--muted2);margin-top:0.75rem;">
    Built on: Young (1975) · Arrow (1951) · Gibbard (1973) · Brams &amp; Sanver (2009) · Pivato (2013, 2014) · Balinski &amp; Laraki (2011)
  </p>
</section>

<!-- FOOTER -->
<footer>
  <p>SOW — Strategic Optimization of Social Welfare &nbsp;·&nbsp;
    <a href="#">Paper</a> &nbsp;·&nbsp;
    <a href="#">Code</a> &nbsp;·&nbsp;
    Olivier Rocca · Vallauris · 2026
  </p>
  <p style="margin-top:0.4rem;color:var(--muted2);">
    Released under the MIT License &nbsp;·&nbsp; Contributions welcome
  </p>
</footer>

</body>
</html>
