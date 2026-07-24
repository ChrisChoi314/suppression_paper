# Massive-graviton suppression paper: figure and analysis release

This repository is for the analytical and numerical results in the massive-graviton suppression paper.

All code needed to regenerate the eight figures in the paper is contained in `reproduce_all_figures.ipynb`.

```text
suppression_paper_code/
|-- README.md
|-- CONTENTS.md
|-- SHA256SUMS
|-- reproduce_all_figures.ipynb
|-- data/
`-- figs/
```

The first code cell imports the packages. The second code cell contains only the corrected ORFs and reusable limiting-integral routines. The remaining code cells reproduce Figures 1 through 8 in order, with each cell explicitly showing its parameter choices, data or cache handling, numerical arrays, plotting commands, PDF save, and inline display.

## Reproducing the figures

Start Jupyter in this directory, open `reproduce_all_figures.ipynb`, and run all cells from top to bottom. We used the following versions of packages:

- Python 3.11.14
- NumPy 1.26.4
- Matplotlib 3.10.8
- SciPy 1.11.4
- pandas 2.3.3

## Figure map

| Paper figure | Notebook section | Output |
|---|---|---|
| 1 | Liang--Trodden and Isi--Stein basis comparison | `figs/liang_old_vs_isi_normalized_grid.pdf` |
| 2 | Tensor distance coherence and NANOGrav distance uncertainties | `figs/tensor_gr_distance_coherence_paper.pdf` |
| 3 | Massive-limit finite-distance factor | `figs/re_pulsar_prod.pdf` |
| 4 | Massive-limit angular shapes | `figs/massive_limit_angular_shapes.pdf` |
| 5 | Massless-limit angular shapes with pulsar terms | `figs/massless_limit_angular_shapes.pdf` |
| 6 | Finite-distance autocorrelations versus `fL` | `figs/autocorrelation_finite_distance_fL.pdf` |
| 7 | Finite-distance autocorrelations versus `1-v_g` | `figs/autocorrelation_finite_distance_vg_scan.pdf` |
| 8 | Vector/scalar sector-fraction heat maps | `figs/sector_fraction_alpha_n_heatmap.pdf` |

## Numerical inputs and seeds

- Figure 1 is deterministic Gauss--Legendre/azimuthal quadrature with no pulsar
  terms.
- Figure 2 uses the three pulsar pairs and uncertainties archived in
  `data/tensor_gr_distance_coherence_paper_pair_markers.csv`. It uses 250,000
  independent positive-truncated Gaussian distance draws with seed `20260723`.
- Figures 3 and 4 are deterministic analytical evaluations.
- Figure 5 uses deterministic angular quadrature at
  `fL = 4500.9528 / 16.03`.
- Figures 6 and 7 use exact finite-`fL` autocorrelation expressions and
  `data/nanograv15_table2_distances.csv`. Their grids and reference values are
  archived in `data/autocorrelation_finite_distance_plot_cache.npz`.
- Figure 8 uses a scrambled Sobol angular sample with seed `0`, 25,000 samples,
  250 separation angles, 120 mass-ratio samples, isotropic `sin(xi) dxi`
  weighting, `f = 1.97679899027005 nHz`, `L_a = 500 ly`, and
  `L_b = 10000 ly`.

`CONTENTS.md` lists every delivered artifact and `SHA256SUMS` records a checksum
for every delivered file other than the checksum file itself.
