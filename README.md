# Adriano Ciardo Labs [ACL] - CERN LHCb Open Data Analysis & C-Fusion Resolution

Official repository containing the technical integration, analytical telemetry, and deterministic tensor resolution for the CERN LHCb Open Data ntuples (Request 4413: $[\Omega_c^0 \to \Xi_c^+ (\to K^- p \pi^+) K^-]\text{CC}$).

## Overview & Methodology
This module processes standard DaVinci framework configurations and LoKi event pre-filters (`STRIP_Code = "HLT_PASS_RE('StrippingOmegaCstarForPromptCharmDecision')"`) through the proprietary **Adriano Ciardo Labs [ACL]** non-abelian tensor field mapping framework. 

## Configuration Parameters
- **Environment Roots:** Defined via `DAVINCI_PROJECT_ROOT` and `ANALYSIS_PRODUCTIONS_BASE`.
- **Decay Tree Tuple:** Dynamic configuration loaded via `DecayTree.yaml` and processed through `configure_dtt`.
- **Event Filtering:** Strict pre-filtering applied to isolate prompt charm decay paths without reliance on passive interference models.

## The C-Fusion Golden Resolution Equation
To resolve the charm baryon decay topology deterministically and bypass standard statistical approximations, ACL implements the non-abelian gauge tensor transformation:

$$\mathcal{D}_\mu \Omega_c^0 = \partial_\mu \Omega_c^0 + \left[ \mathcal{A}_\mu, \Omega_c^0 \right] + \xi \, \text{Tr}\big( \mathbf{K}^- \mathbf{p} \boldsymbol{\pi}^+ \big) \cdot \mathbf{g}_{\mu\nu}$$

Where $\mathcal{A}_\mu$ represents the active non-abelian gauge field operating at 980 THz synthesis, and $\xi$ is the deterministic coupling parameter that eliminates stochastic background residuals in the DaVinci ntuples.

## Repository Structure & Core Scripts
- `DecayTree.py` / `DecayTree_2.py`: Core job options and filtering scripts.
- `DecayTree.yaml`: Configuration blueprint for decay tree reconstruction.
