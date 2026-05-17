# Orbital Analysis: Exoplanet Transit Timing and Light-Curve Modeling

This repository contains a set of Python/Jupyter Notebook workflows for analyzing exoplanet transit light curves from TESS data. The notebooks demonstrate light-curve download and cleaning, transit removal and flattening, Box Least Squares (BLS) searches, phase folding, time binning, and transit timing analysis.

The project was developed as part of an astrophysics research workflow focused on exoplanet transit analysis and orbital-decay-related timing measurements.

## Project Highlights

- Download and inspect TESS light curves with `lightkurve`
- Clean and flatten light curves for transit analysis
- Model transit light curves using the Mandel & Agol analytic transit model
- Run Box Least Squares (BLS) period searches
- Fold light curves by period and bin data in time/phase
- Demonstrate transit timing workflows on systems such as WASP-8, Proxima Centauri, Kepler-1658, WASP-12, and HD 209458

## Repository Structure

```text
.
├── mandelagol.py
├── 01_hot_jupiter_clean_flatten_bls_search.ipynb
├── 02_proxima_centauri_transit_search.ipynb
├── 03_phase_folding_and_time_binning.ipynb
├── 04_kepler1658_sector41_transit_timing.ipynb
├── 05_transit_timing_demonstration.ipynb
├── requirements.txt
└── .gitignore
```

## Notebooks

| Notebook | Description |
|---|---|
| `01_hot_jupiter_clean_flatten_bls_search.ipynb` | Cleans and flattens a hot-Jupiter light curve, removes transits, and performs a BLS search. |
| `02_proxima_centauri_transit_search.ipynb` | Applies a similar TESS light-curve search and transit-analysis workflow to Proxima Centauri. |
| `03_phase_folding_and_time_binning.ipynb` | Demonstrates phase folding and time/binning methods for transit light-curve analysis. |
| `04_kepler1658_sector41_transit_timing.ipynb` | Demonstrates transit timing analysis for Kepler-1658 using TESS Sector 41 data. |
| `05_transit_timing_demonstration.ipynb` | Provides a general transit timing demonstration using TESS light curves. |

## Installation

Create a Python environment and install the dependencies:

```bash
pip install -r requirements.txt
```

## Usage

Launch Jupyter from the repository root so that the notebooks can import `mandelagol.py`:

```bash
jupyter notebook
```

Then open the notebooks in numerical order.

## Main Dependencies

- `numpy`
- `scipy`
- `matplotlib`
- `astropy`
- `lightkurve`
- `lmfit`
- `jupyter`

## Scientific References

The transit model implementation in `mandelagol.py` is based on analytic light-curve calculations from:

- Mandel, K., & Agol, E. (2002). *Analytic light curves for planetary transit searches*. The Astrophysical Journal Letters.
- Eastman, J., & Agol, E. (2008). Related implementation notes and code translation referenced in the source file.

If this code is used for research, please cite the relevant scientific sources and data products.

## Notes

The notebooks were cleaned before upload by removing saved cell outputs and execution counts. This keeps the repository lightweight and easier to review on GitHub.
