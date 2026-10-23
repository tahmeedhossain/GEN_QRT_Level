# Quantum Resource Network

**Live pages:** https://tahmeedhossain.github.io/GEN_QRT_Level/ · **Source:** https://github.com/tahmeedhossain/GEN_QRT_Level

Companion to the [Nonclassicality Network](https://github.com/tahmeedhossain/GEN_GPT_Level) — the same
observable–model–state network method applied to **quantum resource theories**. Thirteen theories
(purity, athermality, asymmetry, coherence, imaginarity, magic, CV Wigner negativity, entanglement,
steering, Bell nonlocality, contextuality, measurement incompatibility, and discord as the cautionary
counterexample) are compiled as one typed, signed graph in which cross-theory edges land on the exact
object they concern:

- Each theory is a **band** of role-resolved nodes: model axioms · **free states** vs **resource states**
  (+ distinguished shared states) · **free operations** vs **resource-utilizing operations** vs
  **impossible-even-with-resources** (no-go theorems as first-class nodes) · **detector** vs
  **quantifier** witnesses.
- **Conversion edges run resource → resource and every one names the operation class (`via`) under
  which it holds** — "resource of A yields resource of B" is not well-formed without that datum.
- Free-set overlap edges run free → free (e.g. {γ} ⊂ incoherent, incoherent ⊂ real,
  SEP ⊂ unsteerable ⊂ Bell-local, STAB ⟂ SEP transversality).
- Negative edges record no-gos with flat-bar terminators (⊣); **no edge means *unsettled***, never
  "false" — the open problems are enumerable mechanically.

| Page | Contents |
|---|---|
| `index.html` | Landing page: overview, the derived propositions QP1–QP5, the gap census QG1–QG10, links. |
| `qrt.html` | The network (v1.1, 2026-10-23): 13 theory bands × role-resolved columns, 116 nodes, 85 edges with verbatim statements, via-classes and provenance-tagged references; edge catalog, theory table, derived & gaps tabs. |

## Motivation

Same three uses as the companion repository:

1. **Automated research-idea generation.** "No edge = unsettled" makes the open questions a queryable
   set. The canonical object here is the **13×13 via-class conversion matrix**: each directed cell
   asks "can a resource of theory A produce a resource of theory B, and under which operation class?"
   This release charts 13 of 156 directed cells; the remaining 143, plus gaps QG1–QG10, are the
   machine-generated agenda.
2. **Easy reviewing.** One claim = one edge with a verbatim statement, references and a per-reference
   provenance tag (`verified` / `knowledge` / `verify`). Checking the review means auditing edges;
   disputing it means filing an issue against an edge id.
3. **Visualization.** Role-resolved bands show at a glance where free sets overlap, where resources
   convert (and through which operations), where spending is powerful (use nodes) and where it is
   provably futile (impossible nodes), and which witnesses merely detect versus actually quantify.

The review process is itself the generator: surveying the field in this format yields its own
research agenda as a by-product.

## Repository layout

```
index.html             landing page + derived-proposition record (GitHub Pages ready)
qrt.html               the network page (standalone)
data/qrt_network.json  machine-readable network (theories, role-resolved nodes, via-annotated edges,
                       derived propositions, gaps, provenance-tagged references)
catalog/qrt_catalog.md prose catalog: axiom-overlap analysis, free-set membership table,
                       conversion list with via-classes, proof sketches, gap list
paper/                 LaTeX concept paper (main.tex, refs.bib, compiled main.pdf)
CITATION.cff           citation metadata (fill in author before release)
LICENSE                MIT (code/pages); cite the underlying papers for the physics
```

## Data schema

Top-level keys of `data/qrt_network.json`:

- `theories`: `{id, name, family, free_states, free_ops, golden_unit, monotones[], refs[]}` — the 13 theories
- `nodes`: `{id, layer, theory, role, label, statement, refs[], status}`
  - `role ∈ {model, free_state, resource_state, dist, free_ops, use_ops, no_ops, detector, quantifier, framework}`
  - `status ∈ {theorem, partial, counterexample, derived}` — epistemic provenance
- `edges`: `{id, from, to, kind, polarity, status, via?, statement, refs[]}`
  - `polarity ∈ {possibility, no_go, structural}` — semantic, orthogonal to status
  - **`via`** on conversion edges = the operation class under which the conversion holds
  - edge-id prefix = group: `MM` axiom links · `SS` state-set overlaps/memberships ·
    `C` conversions · `P` operation lattice · `W` witness links
- `derived_propositions` (QP1–QP5) and `gaps` (QG1–QG10)
- every reference string carries `[verified]` (web-checked 2026-10-23), `[knowledge]`
  (standard result; verify page data before quoting) or `[verify]` (uncertain detail)

**Contributing an edge:** include a precise statement, a reference (or a proof for `derived`),
a kind, a polarity, a status — and for a conversion, the `via` operation class. Closing a cell of
the 13×13 conversion matrix is the canonical contribution.

## Census (v1.1)

116 nodes · 85 edges (38 possibility · 13 no-go · 34 structural; 68 theorem · 12 derived ·
3 partial · 2 counterexample) · 13 / 156 directed conversion cells charted (143 uncharted) ·
4 impossible-process nodes (thermal coherence distillation & work locking; IO mixed-state
irreversibility; no second law under exact NE + bound entanglement; bound magic + no unit-rate
interconversion) · named problems QG1–QG10.

## Reliability and provenance

- Per-reference three-tier tags: `[verified]` = bibliographic data confirmed by web search on
  2026-10-23 (the ~20 load-bearing cross-theory anchors, including the 2024 generalized quantum
  Stein's lemma proofs and the Lami–Regula irreversibility theorem); `[knowledge]` = standard
  results cited from curation knowledge — verify page numbers before quoting; `[verify]` =
  flagged uncertain author lists / venues / pages — must be checked before any release.
- `derived` items (QP1–QP5 and the elementary membership/overlap edges) are proved or sketched in
  `catalog/` and in the paper. **No novelty pass has been run for QP1–QP5 yet** (unlike the
  companion repository's R-propositions); QP2–QP4 are plausibly folklore. Run one before any
  priority claim.
- Composed statements name the edges they compose, so each is auditable in one step.
- Corrections welcome as issues/PRs; releases record their census.

## Citation

See `CITATION.cff`. Please also cite the original papers carried on the edges you use;
the per-edge `refs` field is the citation of record for compiled results.
