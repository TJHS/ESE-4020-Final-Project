# What Must a Placebo Preserve in Short-Window Market Timing?

ESE 4020 final project (Teddy). Random-feature ridge trained on 12 months appears to time the U.S. stock market (Kelly, Malamud and Zhou, 2024); Nagel (2025) argues it is mechanically volatility-timed momentum. This project reproduces the published result exactly, changes one convention at a time, and asks which properties of the predictor panel a placebo must preserve for the model to make similar trades.

## Files
- `ESE_4020_Final_Project_Paper.pdf`: the paper
- `project.ipynb`: **all the code in one notebook**; reproduces every number, table and figure (reads saved results by default; set the `RUN` flags to `True` to rerun everything, about 2.5 hours on two cores)
- `results/`: result files (JSON), monthly forecasts (`forecasts_monthly.csv`, `main_forecasts.npz`), the pre-specified fresh-period plan (`prereg_fresh.json`)
- `figures/`, `paper_tables/`: generated figures and LaTeX tables used in the paper
- `requirements.txt`: pinned package versions
- `PredictorData2025.xlsx`: Goyal-Welch monthly data
- `baseline.ipynb`, `baseline.png`: baseline checkpoint (first-draft design)

## Data sources
**Goyal-Welch data** (redistributed here with attribution). Direct link: https://docs.google.com/spreadsheets/d/1qwpl2R_DNujpU5YUkk8lacP1tTeMb9iJ. On Amit Goyal's website (https://sites.google.com/view/agoyal145) it is the "Updated data (up to 2025)" link under Goyal and Welch (2008), "A Comprehensive Look at the Empirical Performance of Equity Premium Prediction".

**KMZ replication code and data** (needed only for the exact replication in Table 1; not redistributed here). Download "Replication Code" from the supporting information of Kelly, Malamud and Zhou (2024), *Journal of Finance* 79(1), doi:10.1111/jofi.13298, and unzip it into `kmz_replication/`.

## How to run
```
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute project.ipynb     # or open it and run all cells
```
Every script fixes its random seeds. Penalties are chosen on validation targets 1950-1979; the test period (targets 1980-2025) is scored once; placebo AR(1) models are fitted on data through 1979.
