# Synapse Bio

**A biological discovery-graph mini-lab** — a knowledge graph of genes, proteins, pathways,
diseases and drugs that computes *what is missing but plausible* and ranks those gaps as
candidate discoveries.

**Live:** https://synapse-bio-smoky.vercel.app

> "Early biological breakthrough" = a high-plausibility link the literature has not drawn yet.

## How it finds gaps

A three-layer engine (deterministic, runs entirely in the browser, no keys):

1. **Candidate generation** — ABC / Swanson open discovery (`A–B`, `B–C` ⇒ propose `A–C`)
   plus topology link-prediction (common-neighbours, **Adamic–Adar**), constrained by a
   biological type-rule table.
2. **Evidence-weighted ranking** — `ripeness = plausibility × (1 − localCoverage)`:
   high plausibility + low existing evidence = a ripe, under-studied link.
3. **Fragility** — orphan nodes and bridge edges flag under-studied structure.

## What you can do

- **Graph** — explore the bio knowledge graph; analyses overlay predicted links as dashed edges.
- **Analyses** — 5 presets: whole-graph, disease deep-dive, protein-interaction prediction,
  drug-repurposing scan, orphan scan → ranked candidate cards with supporting-path trails.
- **Findings** — save candidates, triage status, take notes (persists locally).
- **Dashboard** — entity/link counts, evidence distribution, ripe-lead gauge, hubs, fragility.

## Note

The bundled dataset is **synthetic and illustrative** (109 nodes across cancer, inflammation,
neurodegeneration, metabolism, cardiovascular), with deliberately planted, research-relevant
gaps for demonstration. It is **not** a clinical or curated biomedical source.

Sibling of [Synapse](https://synapse-vert-one.vercel.app/).
