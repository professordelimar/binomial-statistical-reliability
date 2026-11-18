# Binomial Statistical Reliability Lab

**Reproducible Monte Carlo experiments for statistics and data science education**

This repository contains the computational materials supporting a study of the distinction between **computational correctness** and **statistical reliability**. Five experiments (E01–E05) use Bernoulli/binomial models, exact benchmarks where available, analytical calculations, and Monte Carlo diagnostics to examine situations in which correctly generated numerical results do not automatically justify reliable inference.

The study uses **synthetic data only**. It does not involve human participants or evaluations of student learning. The proposed teaching activities are intended for possible use in higher-education statistics and data science courses and have not been tested in classrooms.

## Research questions and experiments

| Experiment | Topic | Main diagnostic focus |
| --- | --- | --- |
| **E01 — Convergence and reliability** | Sample-proportion bias, variance, RMSE, and fixed versus standardized error tolerances | Agreement with theoretical moments and exact binomial reliability probabilities |
| **E02 — Sampling distributions** | Binomial sampling and continuity-corrected normal approximation | Maximum CDF discrepancy **at integer thresholds** and exact standardized-region probabilities |
| **E03 — Confidence intervals** | Wald, Wilson, and Clopper–Pearson intervals | Exact binomial coverage, expected width, and Monte Carlo validation |
| **E04 — Dependence and nonstationarity** | Stationary binary Markov chains and two-segment Bernoulli processes | Variance inflation, independence-based interval undercoverage, and concealed changes in local probabilities |
| **E05 — Repeated testing** | Fixed-sample versus sequentially monitored score tests and apparent stabilization | False-positive accumulation and later deviations after short-term numerical stability |

Each definitive Monte Carlo scenario used **9,604 independent replications**. The notebook also includes preliminary, intermediate, and computational-validation stages. Some checks use exact calculations rather than Monte Carlo estimates.

## Repository contents

```text
binomial-statistical-reliability-lab/
├── README.md                  # This guide
├── statistic.ipynb            # Complete research notebook, E01–E05
├── requirements.txt           # Python package requirements (not a lockfile)
├── FILE_MANIFEST.txt          # List of archived files
├── results/                   # CSV tables, configurations, audits, and compressed replications
└── figs/                      # Twelve manuscript figures in PNG format
```

### `statistic.ipynb`

The notebook contains the computational workflow, including model setup, random generation, statistical performance measures, exact binomial calculations, validation checks, and figures. It is organized into successive development and definitive experiment stages. The notebook's rendered outputs and execution counters were cleared in the anonymous supplement; this does **not** mean that the archived numerical results were re-created or changed.

### `results/`

The `results/` directory includes original CSV and compressed `.csv.gz` artifacts. Key final files include:

- **E01:** `E01_Definitive_Convergence.csv`, `E01_Definitive_Reliability.csv`, and `E01_Definitive_Audit.csv`.
- **E02:** `E02_Definitive_Moments.csv`, `E02_Normal_Approximation_Diagnostics.csv`, and `E02_Normal_Region_Coverage.csv`.
- **E03:** `E03_Definitive_Exact_Comparison.csv`, `E03_Definitive_MC_Coverage.csv`, and `E03_Definitive_Statistical_Audit.csv`.
- **E04:** `E04_Definitive_Dependence.csv`, `E04_Definitive_Nonstationarity.csv`, and the corrected audit associated with E04 in the notebook.
- **E05:** `E05_Definitive_Summary.csv`, `E05_Definitive_Stopping_Curve.csv`, `E05_Stability_Summary.csv`, and `E05_Definitive_Audit.csv`.

Other files retain preliminary calculations, computational tests, configurations, intermediate results, compressed replication-level data, and audit records for provenance and notebook compatibility. **Do not interpret a preliminary audit as superseding a corrected or definitive audit.**

### `figs/`

The manuscript uses these original PNG figures (the numbers in filenames are development identifiers; the paper numbers figures consecutively):

- E01: `Figure23_E01_Definitive_RMSE.png`, `Figure24_E01_Definitive_Reliability.png`
- E02: `Figure26_E02_NormalAccuracy.png`, `Figure27_E02_NormalCoverage.png`
- E03: `Figure28_E03_CoverageBySize.png`, `Figure29_E03_CoverageSensitivity.png`, `Figure30_E03_ExpectedWidth.png`
- E04: `Figure31_E04_VarianceInflation.png`, `Figure32_E04_DependenceCoverage.png`, `Figure33_E04_Nonstationarity.png`
- E05: `Figure34_E05_OptionalStopping.png`, `Figure35_E05_ApparentStability.png`

## Setup (Windows PowerShell)

**Recommended starting point:** Python 3.11. The version ranges in `requirements.txt` describe package requirements but have not been verified as a complete environment lockfile.

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
jupyter lab
```

If `py -3.11` is unavailable, install Python 3.11 or use an available compatible Python interpreter. On macOS or Linux, create the environment with `python3 -m venv .venv` and activate it with `source .venv/bin/activate`.

Open `statistic.ipynb` and review the configuration cells before running. Executing all experiments can be computationally intensive. **Run in a separate copy** if you wish to preserve the supplied results and figures. The package has not been validated through a new full end-to-end execution after its preparation.

## Reproducibility and interpretation

1. Inspect the notebook and experiment configurations.
2. Read the definitive summary and audit files in `results/`.
3. Compare the reported Monte Carlo quantities with their theoretical or exact references, noting where only a simulation-based estimate is available.
4. Re-execute the notebook only if required, preferably in a fresh copy of the repository.
5. Confirm that a new execution uses the same model parameters, seeds, software environment, and monitoring rules before comparing output files.

The exact binomial checks and analytical variance expressions are validation references, **not** claims of newly discovered statistical laws. The E04 audit includes a correction to a lag-one moment standard-error calculation; interpret that diagnostic using the corrected analysis.

## Research ethics and availability

All datasets are generated synthetically. No participant, student, clinical, or personally identifiable records are included. This repository documents computational research and possible instructional activities; it does not contain classroom evaluation results.

For a journal submission using **double-anonymous peer review**, keep the GitHub repository **private** until the journal-approved data-access procedure is established. A public GitHub profile or repository history may identify the authors, even when file contents are anonymous. If a public persistent identifier is required, coordinate a suitable anonymized reviewer-access workflow with the journal and the chosen research repository before release.

## License

No reuse license is granted by this README alone. Add an appropriate `LICENSE` file after the authors select the desired terms and confirm any applicable institutional requirements.

## Citation

Citation metadata, publication details, and a repository DOI should be added only after they are assigned. Do not cite a placeholder DOI or assume that a GitHub URL is a permanent research-data identifier.
