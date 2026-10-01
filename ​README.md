# Adriano Ciardo Labs [ACL] - CERN LHCb Open Data Analysis

Official repository containing the technical integration and analytical telemetry for the CERN LHCb Open Data ntuples (Request 4413: $[\Omega_c^0 \to \Xi_c^+ (\to K^- p \pi^+) K^-]\text{CC}$).

## Overview & Methodology
This module processes standard DaVinci framework configurations and LoKi event pre-filters (`STRIP_Code = "HLT_PASS_RE('StrippingOmegaCstarForPromptCharmDecision')"`)[span_0](start_span)[span_0](end_span)[span_1](start_span)[span_1](end_span) through the proprietary **Adriano Ciardo Labs [ACL]** non-abelian tensor field mapping framework. 

## Configuration Parameters
- **Environment Roots:** Defined via `DAVINCI_PROJECT_ROOT` and `ANALYSIS_PRODUCTIONS_BASE`[span_2](start_span)[span_2](end_span)[span_3](start_span)[span_3](end_span).
- **Decay Tree Tuple:** Dynamic configuration loaded via `DecayTree.yaml` and processed through `configure_dtt`[span_4](start_span)[span_4](end_span)[span_5](start_span)[span_5](end_span).
- **Event Filtering:** Strict pre-filtering applied to isolate prompt charm decay paths without reliance on passive interference models.

## Repository Structure
- `DecayTree.py` / `DecayTree_2.py`: Core job options and filtering scripts.
- `DecayTree.yaml`: Configuration blueprint for decay tree reconstruction.
