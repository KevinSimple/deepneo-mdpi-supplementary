# DeepNeo-CL — Supplementary Data

Machine-readable evidence accompanying:

> **Efficient Protein Language Models for Peptide–MHC Ranking: A Leakage-Aware
> Evaluation Protocol under Multiplicity Control**
> *Information* (MDPI), Special Issue *Emerging Trends in Machine Learning and
> Natural Language Processing* — under review.

Every substantive numeric claim in the manuscript traces to one of the ledgers in
[`supplementary_data/`](supplementary_data/). This repository holds **only** that
data, the graphical abstract and the highlights. Model weights, training code,
manuscript sources and all correspondence are not published here.

## Contents

| Path | Contents |
|---|---|
| `supplementary_data/` | 20 JSON ledgers + the 10-bin calibration table (`fig_S1_calibration_bins.csv`) |
| `graphical_abstract.svg` | Graphical abstract |
| `HIGHLIGHTS.md` | What the paper does, and does not, claim |

## Key ledgers

| File | Backs |
|---|---|
| `transphla_decontaminated_eval.json` | Decontamination: 161,652 → 43,509 removed (26.9%) → **118,143** clean rows, and every tabled AUROC/AUPR on both the full and clean sets |
| `transphla_rescored_fusion_fixed.json` | Table 1 point estimates |
| `table2_holm_adjusted.json` | Holm-adjusted per-allele Wilcoxon family (4 comparisons) |
| `paired_bootstrap_ci.json` | Allele-clustered bootstrap 95% CIs on Δ (B = 1000) |
| `ece_calibration_transphla_el.json` + `fig_S1_calibration_bins.csv` | Expected calibration error, **full** TransPHLA EL set (*n* = 161,652) — **not** the decontaminated subset |
| `inductive_reranker_result.json` | The withdrawn rescorer: 0.8279 base → 0.8620 in-sample → **0.4423** held-out |
| `iedb_holdout_nmp42_overlap.json` | 1,364 / 1,365 (99.93%) successor-corpus overlap — a train–test **overlap rate**, not an accuracy |
| `weekly_ranking_v41_2020_2026_singlecol_v2.json` | 46-week IEDB auto_bench ranking board |
| `weekly_perref_wilcoxon_vs_nmp41.json` | Within-allele paired Wilcoxon, 15/12/19, *p* = 0.65 |
| `ablation_ladder.json` | Cumulative ablation, TransPHLA EL full set |
| `per_figure_provenance.json` | Which artefact each figure is rendered from |

## Headline, stated honestly

Under exact (peptide, HLA) decontamination against the NetMHCpan-4.1 training corpus
and a predeclared three-condition rule (DeLong + Holm-adjusted per-allele Wilcoxon +
allele-clustered bootstrap CI), on *n* = 118,143 clean rows:

- DeepNeo-CL fused score and NetMHCpan-4.1 fused score are **tied** — 0.9573 vs 0.9575.
- NetMHCpan-4.1 keeps the **BA-head advantage**, Δ = −0.0137, Holm *p* = 1.7 × 10⁻³.
- That BA-head lead is the **only** multiplicity-robust asymmetry on TransPHLA.

This is an evaluation-protocol study, not a state-of-the-art claim.

## Scope

The v4.1 line only: DeepNeo-CL trained on the official NetMHCpan-4.1 five-fold corpus
and compared with NetMHCpan-4.1 at matched training exposure. Numbers from any other
line are not comparable and do not appear here.

## License

[CC BY 4.0](LICENSE).
