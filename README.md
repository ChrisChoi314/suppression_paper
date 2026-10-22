# Massive-graviton suppression paper: figure and analysis release

This repository contains the analytical and numerical results for the paper
"Suppression of extra polarizations in massive-gravity overlap reduction functions
near the massless limit" by Chris Choi, Tina Kahniashvili, and Barnabas Poczos.

[DOI](https://doi.org/10.5281/zenodo.21542567)

All code needed to regenerate the seven figures is contained in
`reproduce_all_figures.ipynb`.

```text
suppression_paper_code/
|-- README.md
|-- requirements.txt
|-- reproduce_all_figures.ipynb
|-- data/
`-- figs/
```

The first code cell imports the packages and defines the shared ORF routines.
The remaining cells reproduce Figures 1 through 7 in order, save the plots in
`figs/`, and display them in the notebook.

## Reproducing the figures

Install the packages and start Jupyter from this directory:

```bash
python -m pip install -r requirements.txt notebook
jupyter notebook reproduce_all_figures.ipynb
```

Run all cells from top to bottom. The code was checked with:

- Python 3.11.14
- NumPy 1.26.4
- Matplotlib 3.10.8
- SciPy 1.11.4

## Figure map

| Paper figure | Notebook section | Output |
|---|---|---|
| 1 | Tensor distance coherence | `figs/tensor_gr_distance_coherence_paper.pdf` |
| 2 | Massive-limit angular shapes | `figs/massive_limit_angular_shapes.pdf` |
| 3 | Cross-correlations versus group velocity | `figs/cross_correlation_vg_log_L500_L2000_xi30.pdf` |
| 4 | Autocorrelations versus `1-v_g` | `figs/autocorrelation_finite_distance_one_minus_v_scan.pdf` |
| 5 | Massless-limit angular shapes with pulsar terms | `figs/massless_limit_angular_shapes.pdf` |
| 6 | Effective ORFs with scalar suppression | `figs/effective_orf_scalar_suppression_massless_panels.pdf` |
| 7 | Angular RMS convergence toward GR | `figs/scalar_suppression_convergence_rms.pdf` |

PNG copies are also saved.

## Numerical inputs

- Figure 1 uses the central pulsar distances in
  `data/tensor_gr_distance_coherence_paper_pair_markers.csv`. This is the only
  required data file.
- Figures 3, 6, and 7 use `L_a=500 ly`, `L_b=2000 ly`, and `f=1/(16.03 yr)`.
- Figure 4 uses `fL=10^4`, with both axes on logarithmic scales.
- Figure 5 uses `fL=4500.9528/16.03`.
- Figures 6 and 7 use `A_S=0.5`. Figure 7 has four panels, with `n_S=0,1,2,3`.

All calculations are deterministic; no random seeds are needed. Numerical arrays
and parameter reports are saved in `data/` when the notebook runs.
