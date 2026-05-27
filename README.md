# NDLAr-2x2 Proton Sample Distributions

A focused study of proton track kinematics in the ND-LAr 2×2 detector using MiniRun6.5 MC and sandbox data CAFs collected with the NuMI beam at Fermilab. Angular and track-length distributions of reconstructed proton candidates are compared between simulation and data.
All plots produced by the macros listed below are documented in the technote at docDB:12345.

---

## Input File Lists

| File | Description |
|------|-------------|
| `MiniRun6p5.txt` | List of MiniRun6.5 MC CAF files used as input to the MC analysis script |
| `sandbox_v11.txt` | List of sandbox data CAF files used as input to the data analysis script |

---

## Analysis Scripts

| File | Description |
|------|-------------|
| `purity_dlp_multiplicity.cc` | Processes MC CAF files. Applies CC νµ selection with truth-matching cuts (`goodInteraction`), fills track multiplicity and kinematic histograms, and writes output histograms and trees to `output.root` |
| `data.cc` | Processes data CAF files. Applies the same reco-level selection as the MC (without truth-matching cuts), fills equivalent histograms, and writes output to `sandbox_v11_minervaOff_geomContainRecoOnly_Lgt3cm_300cm_endZneg0to5cmVeto_cosZgtNeg0p9.root` |

---

## Output ROOT Files

| File | Description |
|------|-------------|
| `output.root` | Output produced by `purity_dlp_multiplicity.cc`; contains MC histograms and nusystematics weight trees |
| `sandbox_v11_minervaOff_geomContainRecoOnly_Lgt3cm_300cm_endZneg0to5cmVeto_cosZgtNeg0p9.root` | Output produced by `data.cc`; contains data histograms with the full reco selection applied |

---

## Plotting Macros

### Style
| File | Description |
|------|-------------|
| `protoDUNEStyle.C` | ROOT plotting style macro; sets the `DUNE:ND-LAr 2x2` label and standard pad/axis formatting used across all plots |

### Proton Kinematics — Data/MC Comparisons
| File | Description |
|------|-------------|
| `plot_dataMC_proton_cosTheta_GENIE.C` | Plots proton cos θ data/MC comparison with GENIE systematic uncertainty band |
| `plot_dataMC_proton_length_GENIE.C` | Plots proton track length data/MC comparison with GENIE systematic uncertainty band |
| `plot_dataMC_proton_g4rw_band.C` | Plots proton kinematic data/MC comparison with Geant4Reweighting (G4RW) systematic uncertainty band |
| `plot_dataMC_proton_detector_band.C` | Plots proton kinematic data/MC comparison with detector response and TPC physics systematic uncertainty band |
| `plot_dataMC_proton_combined_band.C` | Plots proton kinematic data/MC comparison with the combined systematic uncertainty band (GENIE + Geant4 + Detector) |
