# Manifest: where every table and figure comes from

| Paper item | Produced by (section of `project.ipynb`) | Result file and keys |
|---|---|---|
| Table 1 (published, exact replication, ladder, benchmarks) | notebook §2 (`exp_kmz2`), §6 (`exp_attr`) | `results/kmz2.json` (`exact`, `exact_linear_z1e3`, `ladder`, `bench_*`); `results/attr.json` (`signals`) |
| Table 2 (placebo grid, paired gaps) | notebook §3 (`exp_main`) | `results/main.json` (`grid`) |
| Table 3 (detection rates) | notebook §5 (`exp_sim`, three runs) | `results/sim.json`, `results/sim_dp_strong.json`, `results/sim_ltr.json` |
| Figure 1 (complexity, E1 and E2) | notebook §3 (`exp_main`), §9 (`make_figs`) | `results/main.json` (`curve`) -> `figures/fig_complexity.pdf` |
| Figure 2 (mechanism) | notebook §3, §4, §9 | `main.json` (`grid`), `mech.json` (`similarity`, `weights`) -> `figures/fig_mechanism.pdf` |
| Appendix: review response, implementation details | text | - |
| Appendix: placebo definitions, MC precision (Table 4), joint bands (Table 5) | notebook §3 (`exp_main`) | `main.json` (`grid.*.mc_se`, `joint`) |
| Appendix: complexity curve (Table 6), post-2020 extension (Table 7) | notebook §3 (`exp_main`) | `main.json` (`curve`, `curve_increase_12_to_12000`, `grid.*.post`) |
| Appendix: attribution (Table 8) | notebook §6 (`exp_attr`) | `attr.json` (`attribution`) |
| Appendix: intercept (Table 9), ablation (Table 10) | notebook §4 (`exp_mech`) | `mech.json` (`intercept`, `ablation`) |
| Appendix: fresh period (Table 11) | notebook §4 (`exp_mech`) | `mech.json` (`fresh`), plan in `prereg_fresh.json` |
| Appendix: matched networks (Table 12) | notebook §7 (`exp_mlp2`) | `mlp2.json` |
| Appendix: implementation and costs (Table 13), Figure 3 | notebook §6, §9 | `attr.json` (`implementation`); `figures/fig_cumpnl.pdf` |
| Course ridge baseline (Table 1 row), position correlations, weight distributions, post-2020 intervals | notebook §8 (`exp_extra`) | `results/extra.json` |
| LaTeX table bodies | notebook §9 (`make_tables`) | `paper_tables/*.tex` (generated from the JSON files; no hand-copied numbers) |
| Monthly forecasts | notebook §9 (`export_forecasts`) | `results/forecasts_monthly.csv` (averaged positions), `results/main_forecasts.npz` (every draw) |

All code is in `project.ipynb`; its sections run in this order. Each experiment is one function (`exp_kmz2`, `exp_main`, `exp_mech`, `exp_sim`, `exp_attr`, `exp_mlp2`, `exp_extra`) followed by a cell that displays its results.
