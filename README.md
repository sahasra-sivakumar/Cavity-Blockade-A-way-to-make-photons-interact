# Photon Blockade in a Driven Jaynes–Cummings Cavity

A computational quantum-optics project studying how coupling a two-level atom to a driven cavity changes photon statistics.

Author: Sahasra Sivakumar  
Context: Quantum Information with Atoms and Photons project

## Overview

The project compares an uncoupled, coherently driven cavity with a strongly coupled atom–cavity system. It uses open-system simulations to investigate steady-state populations, photon-number statistics, and frequency-dependent signatures of photon blockade.

## Physical model

With hbar set to one, the drive-frame Hamiltonian is

```math
H = \Delta_c a^\dagger a + \Delta_a \sigma_+\sigma_-
  + g(\sigma_+a+\sigma_-a^\dagger)+Ea+E^*a^\dagger,
```

where the detunings are cavity/atomic frequency minus drive frequency. Cavity loss and atomic spontaneous emission are included through

```math
\dot\rho=-i[H,\rho]+\kappa\mathcal D[a]\rho
+\Gamma\mathcal D[\sigma_-]\rho,
\qquad
\mathcal D[L]\rho=L\rho L^\dagger-\tfrac12\{L^\dagger L,\rho\}.
```

The equal-time correlation is

```math
g^{(2)}(0)=\frac{\langle a^\dagger a^\dagger aa\rangle}{\langle a^\dagger a\rangle^2}.
```

## Computational workflow

1. Simulate the uncoupled driven cavity and compare its steady-state photon distribution with a Poisson distribution.
2. Introduce atom–cavity coupling and drive the lower one-excitation polariton.
3. Examine photon populations and equal-time correlations.
4. Sweep the drive frequency to compare transmission and correlation signatures.

## Results reported in the project

- Uncoupled benchmark: drive amplitude 1.0 and cavity decay rate 0.5 give a steady-state mean photon number of 16; the report uses a Fock-space truncation of 50.
- Coupled example: coupling 5, cavity decay 0.1, atomic decay 0.05, and drive amplitude 0.05.
- The coupled calculation reports strong suppression of multiphoton occupation and equal-time correlations below one at the polariton resonances.
- Frequency sweeps investigate vacuum-Rabi-split peaks and two-photon resonances.

These are report-derived findings; the notebook has not been independently rerun for this documentation.

## Repository contents

- [Simulation notebook](<photon_blockade_notebook (1).ipynb>)
- [Full project report](<photon_blockade__Copy_ (1).pdf>)

## Running the project

The report identifies Python and QuTiP as the simulation tools. Open the notebook in a Jupyter-compatible environment, review its imports and parameters, and execute cells in order. Exact dependency versions, additional imports, and a clean-environment execution procedure still need to be verified against the notebook. No pinned environment is claimed here.

## Scope and limitations

This is a numerical study, not a new experimental observation or a source-device implementation. Photon blockade means suppression, rather than absolute exclusion, of multiphoton occupation. Convergence with Hilbert-space cutoff and integration time should be checked when changing parameters. Interpret normalized correlations cautiously when the mean population is very small.

The report's rotating-frame derivation, blockade-gap conventions, and strong-drive steady-state interpretation require a technical consistency review before being reused verbatim. This README therefore summarizes the model and reported observations without repeating those detailed claims.

## References

- K. M. Birnbaum et al., “Photon blockade in an optical cavity with one trapped atom,” Nature 436, 87–90 (2005).
- J. R. Johansson, P. D. Nation, and F. Nori, “QuTiP: An open-source Python framework for the dynamics of open quantum systems,” Computer Physics Communications 183, 1760–1772 (2012).
