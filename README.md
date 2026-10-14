# kozai-lidov-paper-code
Code accompanying "Relativistic Destruction of the Kozai-Lidov Resonance in Cluster-Hardened Black Hole Triples": simulations of Kozai-Lidov oscillations in black-hole triples and the resulting eccentric gravitational-wave inspirals.

# kozai-lidov-paper-code

Code accompanying "Relativistic Destruction of the Kozai-Lidov Resonance in Cluster-Hardened Black Hole Triples": simulations of Kozai-Lidov oscillations in black-hole triples and the resulting eccentric gravitational-wave inspirals.

Paper: [arXiv:XXXX.XXXXX](https://arxiv.org/abs/XXXX.XXXXX)

## What this code does

For a fiducial hierarchical triple (15 + 15 Msun inner binary, 30 Msun tertiary), the notebook:

1. Integrates the triple directly (REBOUND/REBOUNDx, with 1PN precession) to measure the Kozai-Lidov eccentricity cycle.
2. Hardens the inner binary with an orbit-averaged Peters inspiral and generates the eccentric gravitational-wave harmonics.
3. Measures the faithfulness (mismatch) between the Kozai-Lidov and circular waveforms using the aLIGO PSD.
4. Maps where general-relativistic precession quenches Kozai-Lidov oscillations, using a double-averaged secular solver validated against direct N-body runs.
5. Builds the reduced KL + 1PN phase-space picture and tests robustness to the initial KL phase.

## Installation

Python [3.X] is recommended.

```
git clone https://github.com/barkael327-a11y/kozai-lidov-paper-code.git
cd kozai-lidov-paper-code
pip install -r requirements.txt
jupyter notebook KL_paper_code.ipynb
```

Dependencies: numpy, scipy, matplotlib, rebound, reboundx, pycbc.

## How to run

Open `KL_paper_code.ipynb` and run all cells **in order, top to bottom**. Later cells use variables and functions defined in earlier ones. Each cell starts with a one-line comment describing what it does. Outputs are written to `results/` (data), `figures/` and `arxiv_figs/` (plots), which are created automatically and are not tracked in this repository.

## Which cells produce which results

| Result | Cells |
|---|---|
| Fiducial KL evolution, inspiral, waveforms | 1-8 |
| Handoff-separation sweep (blind-spot test) | 9 |
| Hardening ladder and adiabaticity check | 10-11 |
| Saving results to `results/*.npz` | 12 |
| Figure 2: GR-quenching map | 13-16, 21 |
| Figure 3: phase-space data (atlas and Hamiltonian) | 17-18 |
| Figure 5: initial KL-phase robustness | 19-20 |

Approximate runtimes: the direct N-body KL integration (cell 4) takes several minutes; the dense phase-space atlas (cell 17) about 2-3 minutes; the Hamiltonian (cell 18) about 10 seconds. The other cells were not timed.

## Not included

This notebook does not contain the plotting code for Figures 1, 3, 4 and 6 [edit this list to match what you add].

## License

MIT. See [LICENSE](LICENSE).

## Citation

If you use this code, please cite the paper:

```
[Your Name], "Relativistic Destruction of the Kozai-Lidov Resonance in
Cluster-Hardened Black Hole Triples", arXiv:XXXX.XXXXX (2026).
```

Once the Zenodo DOI exists, add: `Code: https://doi.org/10.5281/zenodo.XXXXXXX`
