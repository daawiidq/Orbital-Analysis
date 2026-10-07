# Exoplanet Light Curves and Transit Timing

Python notebooks exploring astronomical time series: data cleaning, periodic-signal searches, phase folding, nonlinear fitting, and timing residuals.

**Start here:** [phase folding and binning](03_phase_folding_and_time_binning.ipynb), then [Kepler-1658 transit timing](04_kepler1658_sector41_transit_timing.ipynb). Each notebook now explains its question, assumptions, and interpretation limits.

## Workflow

TESS light curves → quality cuts and normalization → period search or transit fitting → diagnostic plots and timing residuals.

| Notebook | Target | Analysis |
| --- | --- | --- |
| [01](01_hot_jupiter_clean_flatten_bls_search.ipynb) | WASP-8 | Flattening, known-transit masking, residual BLS search |
| [02](02_proxima_centauri_transit_search.ipynb) | Proxima Centauri | Flare filtering and exploratory BLS search |
| [03](03_phase_folding_and_time_binning.ipynb) | WASP-12 | Time bins and phase folding at twice the reference period |
| [04](04_kepler1658_sector41_transit_timing.ipynb) | Kepler-1658 | Transit-center fits, linear ephemeris, observed-minus-calculated residuals |
| [05](05_transit_timing_demonstration.ipynb) | HD 209458 | A second transit timing workflow |

## Run

Use Python 3 in a virtual environment, from the repository root:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook
```

Windows PowerShell: activate with `.venv\Scripts\Activate.ps1`. Internet access is needed to download archive data. Dependencies are not locked to a fully reproduced environment.

## Reproducibility and interpretation

- These are exploratory notebooks, with manual cuts and target-specific parameters. Inspect the raw data and masks before rerunning an analysis.
- Archive products are selected by numeric search-result indices. Those indices can change. Inspect the search table and record the sector, author, cadence, and product identifier before using a result.
- Notebook 04's filename retains the original Sector 41 label; its current index-based selection does **not** guarantee Sector 41.
- Stored outputs are cleared. The current documentation update includes syntax checks, not a fresh end-to-end execution against the archive; no new numerical results are claimed.
- A BLS peak is a candidate periodic signal, not a discovery. Timing residuals alone do not establish orbital decay. Correlated noise, model assumptions, ephemeris uncertainty, and the observing baseline matter.

## Model attribution

`mandelagol.py` is a reused analytic transit-model implementation. Its original header and credits are retained. The analysis notebooks use this model; the underlying analytic model is not claimed as original work.

Follow the source header's attribution to Mandel & Agol (2002), *Analytic Light Curves for Planetary Transit Searches*, and Eastman & Agol (2008). Cite the relevant TESS data products and Lightkurve when using the analysis in research.
