<h1 align="center">🎉 Awesome Machine Learning Force Fields 🔥</h1>

---

<p align="center">
<img width="768px" alt="Awesome ML Force Fields" src="assets/logoGithub.svg">
</p>

<p align="center">
<img src="https://img.shields.io/badge/Awesome-Survey-8A2BE2" alt="Awesome Survey">
<img src="https://img.shields.io/badge/Focus-Long--Range%20%26%20Reactive%20%26%20ConstP-blue" alt="Long Range, Reactive & ConstP">
<img src="https://img.shields.io/badge/Topics-Electrostatics%20%7C%20Dispersion%20%7C%20Reactions%20%7C%20ConstP-4BC88C" alt="Topics">
<br>
<img src="https://img.shields.io/badge/Update%20🔥-2026.05.18-red" alt="Update">
<img src="https://img.shields.io/badge/Maintained-actively-brightgreen" alt="Actively Maintained">
<img src="https://img.shields.io/badge/PRs-Welcome-orange" alt="PRs Welcome">
<br>
<br>
<b>🔥 This is a living repository, actively maintained and continuously updated with new papers, datasets, benchmarks, and code releases. 🔥</b>
<br>
<br>
You can click on <b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/eyes-emoji.png" alt="Watch Icon"/> Watch</b> and <b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/star-emoji.png" alt="Star Icon"/> Star</b> to get the latest updates at any time.
<br>
<br>
<b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/eyes-emoji.png" alt="Watch Icon"/> Watch</b> Me ! <b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/eyes-emoji.png" alt="Watch Icon"/> Watch</b> Me ! <b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/eyes-emoji.png" alt="Watch Icon"/> Watch</b> Me !
<br>
<b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/star-emoji.png" alt="Star Icon"/> Star</b> Me ! <b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/star-emoji.png" alt="Star Icon"/> Star</b> Me ! <b><img width="16" src="https://img.icons8.com/emoji/48/FFD700/star-emoji.png" alt="Star Icon"/> Star</b> Me !
</p>

---

## 📚 Table of Contents

- [💙 News](#-news)
- [Introduction](#introduction)
- [🧭 Taxonomy](#-taxonomy)
- [🌟 Long-Range Interactions](#-long-range-interactions)
  - [📖 Reviews and Perspectives](#-reviews-and-perspectives-long-range)
  - [🔬 Models and Methods](#-models-and-methods-long-range)
  - [🧪 Datasets](#-datasets-long-range)
  - [🏆 Benchmarks](#-benchmarks-long-range)
- [🔥 Reactive Chemistry](#-reactive-chemistry)
  - [📖 Reviews and Perspectives](#-reviews-and-perspectives-reactive)
  - [🔬 Models and Methods](#-models-and-methods-reactive)
  - [🧪 Datasets](#-datasets-reactive)
  - [🏆 Benchmarks](#-benchmarks-reactive)
- [⚡ Constant-Potential Electrochemistry](#-constant-potential-electrochemistry)
  - [📖 Foundations and Reviews](#-foundations-and-reviews-constant-potential)
  - [🔬 Models and Methods](#-models-and-methods-constant-potential)
  - [🧩 Adjacent and Cautionary Methods](#-adjacent-and-cautionary-methods)
  - [🧪 Codes, Data, and Reproducibility](#-codes-data-and-reproducibility)
- [Contributing](#contributing)
- [Cite This Repository](#cite-this-repository)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## 💙 News

**[2026/05/18] [V0.5] Added constant-potential electrochemistry MLFFs.**

- Added a dedicated section for MLFFs that treat electrode potential or electron chemical potential as an external thermodynamic variable
- Added CP-MLFF/MACE, CPMPNN, DP-Ne/GC-PIHMC, DPchi, veNNP, and DP-QEq references
- Added validation guidance for variable electron number, Fermi level/work-function prediction, and grand-canonical sampling

**[2026/05/06] [V0.4] Expanded reactive MLFF review and perspective list.**

- Added focused reviews on reactive MLIPs, reaction PESs, transition-state prediction, and data generation
- Added adjacent equivariant/general MLIP, catalysis, and electrochemistry perspectives relevant to reactive workflows
- Corrected the Chemical Reviews 2026 citation for reactive MLIPs

**[2026/05/05] [V0.3] Merged long-range and reactive MLFF repositories.**

- Unified two focused repositories into one comprehensive resource
- Reorganized structure: Long-Range Interactions + Reactive Chemistry
- Each theme divided into: Reviews, Models, Datasets, Benchmarks
- Added 14 reactive MLFF entries

**[2026/05/04] [V0.2] Added 7 new papers on long-range interactions.**

- Added Euclidean Fast Attention, LES, SO3LR, CHGNet, M3GNet
- Added BioFragment Database and DES370K datasets

**[2026/05/01] [V0.1] Initial release.**

- Created focused navigation lists for long-range and reactive MLFFs
- Added first taxonomy, dataset links, and core papers

---

## Introduction

Modern machine learning force fields face three coupled challenges:

**Long-Range Interactions**: Most MLFFs use finite cutoffs and local decomposition, which works well for many systems but fails for charged molecules, polar liquids, interfaces, ionic materials, and systems where electrostatics, dispersion, or polarization remain relevant beyond the cutoff.

**Reactive Chemistry**: Models trained only on equilibrium conformers may have excellent force errors near minima but fail along bond-breaking pathways, transition states, ionic/radical regions, or high-temperature reactive trajectories.

**Constant-Potential Electrochemistry**: Electrochemical interfaces add another coupled difficulty: the electrode potential is externally controlled, while electron number, interfacial charge, Fermi level/work function, solvent structure, and reaction barriers can all change during sampling.

This repository collects methods, datasets, and benchmarks that explicitly address these challenges.

### ✨You are welcome to contribute.✨

If you discover missing work, please submit a pull request or issue. Include a stable paper link, code/data link when available, and a one-sentence explanation.

---

## 🧭 Taxonomy

### Long-Range Interaction Methods

| Family | Typical ingredients | Strength | Typical caveat |
|---|---|---|---|
| Charge / dipole learning | Atomic charges, molecular dipoles, charge constraints, QEq | Physically interpretable electrostatics | Needs charge/dipole labels or reliable constraints |
| Wannier-center / electronic-center learning | MLWCs, electronic response variables | Strong for insulating periodic systems | Requires extra electronic-structure labels |
| Ewald / PME augmentation | Explicit reciprocal-space summation | Correct asymptotic periodic electrostatics | Engineering complexity and charge neutrality details |
| Latent reciprocal variables | Hidden charges or latent fields + Ewald/Fourier layers | Can learn from energy/force only | Interpretability and transfer need validation |
| Global message passing | Ewald features, global nodes, Fourier convolution | Adds nonlocal communication to GNNs | May still need physics priors for asymptotics |
| Dispersion correction | D3/D4/MBD or learned dispersion tail | Cheap and robust for vdW | Double-counting if base model already learned it |

### Reactive MLFF Problem Map

Reactive MLFFs are better organized as a workflow plus a chemistry scope, rather than as a single flat list of methods. The key distinction is whether a resource helps generate reactive data, fit a potential, search reaction paths, or validate chemical correctness.

#### Reactive MLFF Workflow

| Stage | Typical methods or data | What it solves | Typical caveat |
|---|---|---|---|
| Reactive data generation | NEB, IRC, GSM, TS searches, AFIR, endpoint/geodesic interpolation | Samples bond-breaking/forming regions and transition paths | Expensive QM optimization or mechanism bias |
| Rare-event sampling | High-T reactive MD, nanoreactors, umbrella sampling, metadynamics | Reaches reactive configurations not seen near minima | Can generate noisy, unphysical, or redundant structures |
| Active learning | Ensembles, query-by-committee, uncertainty-driven MD, DP-GEN-style loops | Expands the training set where the current MLIP is unreliable | Uncertainty indicators need filtering and OOD checks |
| Reactive model fitting | ANI-1xnr, AIMNet2-rxn/NSE, MACE, NequIP, Allegro, NewtonNet | Learns reactive PESs for target chemistry and dynamics | Element, charge, spin, phase, and metal scope must be respected |
| Path and TS workflows | ML-NEB, Sella, PySisyphus, IRC, ML Hessians | Accelerates TS optimization, reaction paths, and mechanism exploration | ML-found paths need QM validation for critical claims |
| Chemical validation | Barrier heights, reaction energies, TS modes, Hessians, graph matching | Tests whether the learned PES gives the right chemistry | Force RMSE alone is not sufficient |

#### Reactive Chemistry Scopes

| Scope | Representative systems | Special difficulty |
|---|---|---|
| Closed-shell organic reactions | Pericyclic reactions, substitutions, rearrangements, bond dissociation | Coverage of TS and off-equilibrium reaction paths |
| Radical and open-shell chemistry | Combustion, polymerization, radical intermediates | Spin states, charge states, and electronic-state transferability |
| Condensed-phase reactivity | Nanoreactors, solution reactions, prebiotic chemistry, biofuel chemistry | Many species, rare events, solvation, and long trajectories |
| Surface catalysis | Methane activation, CO2 reduction, adsorbate reactions | Surfaces, adsorbates, PBCs, and metal-support interactions |
| Organometallic catalysis | Pd cross-coupling, ligand effects, transition-metal TSs | Oxidation states, coordination changes, ligand diversity, spin |
| Electrolyte and electrochemistry | Electrolyte decomposition, SEI chemistry, charged interfaces | Ions, radicals, long-range electrostatics, and reactive solvation |

### Constant-Potential Electrochemistry Problem Map

Constant-potential MLFFs are not just ordinary MLFFs trained at several fixed charges. The stricter goal is to emulate an electronically grand-canonical or electrode-reservoir calculation where potential, electron chemical potential, or work function is controlled and charge/electron number can respond.

| Axis | What the MLFF must learn or control | Typical caveat |
|---|---|---|
| External electrode condition | Applied potential, electron chemical potential, work function, or Fermi level reference | Reference scales, PZC alignment, and implicit/explicit solvent conventions differ across papers |
| Variable electron number / charge | Total excess electrons, atomic charge redistribution, or QEq/conductor charges | Partial charges are model-dependent and not unique observables |
| Grand-canonical energetics | Grand potential, forces, and sometimes Fermi level/work function in one model | Forces should be consistent with the thermodynamic potential used for sampling |
| Double-layer response | Explicit solvent/ions, long-range electrostatics, capacitance, and field screening | Finite-size, PBC neutrality, and countercharge choices can dominate trends |
| Reaction sampling | CP-MD, GC-HMC, slow growth, umbrella sampling, or active learning near reaction paths | Data are usually system- and potential-window-specific rather than universal |

---

## 🌟 Long-Range Interactions

---

### 📖 Reviews and Perspectives (Long-Range)

| Resource | Focus | Summary |
|---|---|---|
| [Neural network potentials for chemistry: concepts, applications and prospects](https://pubs.rsc.org/en/content/articlelanding/2023/dd/d2dd00102k) (Digital Discovery, 2023) | Comprehensive review of NN-based PESs for chemistry | Covers theoretical background, NN architectures, descriptors, PES construction workflows, knowledge transfer, applications in spectroscopy and dynamics. |
| [Neural network potentials: a concise overview of methods](https://doi.org/10.1146/annurev-physchem-082720-034254) (Annu. Rev. Phys. Chem., 2022) | Concise overview of NNP methods across four generations | Systematic classification from first-generation to fourth-generation potentials with nonlocal charge transfer. |
| [Four generations of high-dimensional neural network potentials](https://doi.org/10.1021/acs.chemrev.0c00868) (Chem. Rev., 2021) | Comprehensive review of HDNNP evolution including long-range treatment | Reviews four generations: from low-dimensional systems to high-dimensional local models, then adding long-range electrostatics and nonlocal charge transfer. |
| [Machine learning potentials for extended systems: a perspective](https://doi.org/10.1140/epjb/s10051-021-00156-1) (Eur. Phys. J. B, 2021) | Perspective on ML potentials for materials with long-range interactions | Discusses locality exploitation, long-range electrostatics, and non-local charge transfer in ML potentials for extended systems. |
| [Long-range electrostatics made easier](https://doi.org/10.1063/5.0316886) (J. Chem. Phys., 2026) | Perspective on LES framework design principles | Distills two key principles: use Coulomb functional with environment-dependent charges, and avoid training on ambiguous DFT partial charges. |
| [When short-range models fall short](https://doi.org/10.1063/5.0031215) (J. Chem. Phys., 2021) | Analysis of long-range interaction necessity in ML models | Demonstrates that while local representations suffice for condensed phases, short-range ML models fail for cluster and vapor phases. |
| [General-purpose ML potentials with nonlocal charge transfer](https://doi.org/10.1021/acs.accounts.0c00689) (Acc. Chem. Res., 2021) | Account of fourth-generation NNPs capturing nonlocal phenomena | Overview of machine learning potentials that can describe long-range charge transfer and electronic effects. |

---

### 🔬 Models and Methods (Long-Range)

<details><summary>Charge, Dipole, and QEq Models</summary>

| Method | Main idea | Summary |
|---|---|---|
| [PhysNet](https://doi.org/10.1021/acs.jctc.9b00181) (J. Chem. Theory Comput., 2019) | Predicts partial charges and dipoles together with energies/forces | Multitask energy/charge learning; predicted charges enter an explicit electrostatic term and dipoles are trained as observables. |
| [SpookyNet](https://doi.org/10.1038/s41467-021-27504-0) (Nat. Commun., 2021) | Adds electronic degrees of freedom and nonlocal effects | Uses total charge/spin embeddings, nonlocal interactions, and analytic electrostatic/dispersion corrections. |
| [4G-HDNNP](https://doi.org/10.1038/s41467-020-20427-2) (Nat. Commun., 2021) | Neural atomic energy + global charge equilibration | Uses QEq over NN-predicted electronegativities; the resulting global charges feed both long-range electrostatics and short-range atomic networks. |
| [TensorMol-0.1](https://doi.org/10.1039/C7SC04934J) (Chem. Sci., 2018) | Short-range NN model chemistry augmented with learned charges and long-range physics | Historical hybrid NNP combining Behler-Parrinello short-range terms, dipole-fitted charges, damped Coulomb, and vdW corrections. |
| [AIMNet2](https://github.com/isayevlab/aimnetcentral) | Charge-aware neural potential with Ewald/DSF and D3 support | Current AIMNetCentral models include spin/charge-aware variants and long-range electrostatics support. |
| [AIMNet-NSE](https://doi.org/10.1038/s41467-021-24904-0) (Nat. Commun., 2021) | Neural sum of energies approach with charge prediction | Neural spin-charge equilibration conserves total spin charges by construction. |
| [BAMBOO](https://doi.org/10.1038/s42256-025-01009-7) (Nat. Mach. Intell., 2025) | Electrolyte force-field framework with ML charges | Graph equivariant transformer MLFF for liquid electrolytes with semi-local, QEq electrostatic, and D3 dispersion terms. |
| [HIPNN Charge](https://doi.org/10.1021/acs.jpclett.8b00684) (J. Phys. Chem. Lett., 2018) | Hierarchical interacting particle neural network with charge prediction | Uses HIP-NN to infer partial charges from molecular dipoles. |
| [SCFNN](https://doi.org/10.1038/s41467-022-29243-2) (Nat. Commun., 2022) | Self-consistent field neural network for charge equilibration | Separates Gaussian-truncated short-range physics from long-range electric-field response. |
| [BpopNN](https://doi.org/10.1021/acs.jctc.0c00217) (J. Chem. Theory Comput., 2020) | Bond-order potential neural network with charge transfer | Treats DFT energy as a function of atom-based electron populations from CDFT. |
| [CENT](https://doi.org/10.1103/PhysRevB.92.045131) (Phys. Rev. B, 2015) | Charge equilibration via neural network technique | Learns environment-dependent electronegativities via NN to predict atomic charges through charge equilibration. |

</details>

<details><summary>Ewald, PME, Fourier, and Reciprocal-Space Models</summary>

| Method | Main idea | Summary |
|---|---|---|
| [DPLR](https://doi.org/10.1063/5.0083669) (J. Chem. Phys., 2022) | Learns Wannier centers and evaluates long-range electrostatics with Deep Potential | Adds Gaussian charges at ionic sites and MLWC-derived electronic sites to DP. |
| [DeepWannier for Dielectric Response](https://doi.org/10.1103/PhysRevB.102.041121) (Phys. Rev. B, 2020) | Learns Wannier centers for dielectric properties | Learns MLWC centers with a symmetry-preserving DNN. |
| [EwaldMP](https://github.com/arthurkosmala/EwaldMP) | Adds Ewald-based long-range message passing to molecular graphs | Reference implementation is available from the linked repository. |
| [LES](https://doi.org/10.1038/s41524-025-01577-7) (npj Comput. Mater., 2025) | Learns latent variables and applies Ewald summation | Predicts latent variables from local descriptors and couples them globally through Ewald summation. |
| [LES augmentation](https://doi.org/10.1021/acs.jctc.5c01400) (J. Chem. Theory Comput., 2026) | Standalone LES library attached to CACE, MACE, NequIP, Allegro, CHGNet, UMA | Standalone PyTorch LES module for retrofitting short-range MLIPs. |
| [SOG-Net](https://arxiv.org/abs/2502.04668) (arXiv, 2025) | Learns sum-of-Gaussians long-range kernels with Fourier convolution | Learns latent variables and sum-of-Gaussians Fourier convolution kernels. |
| [CACE-SOG](https://doi.org/10.1063/5.0303312) (J. Chem. Phys., 2026) | Couples CACE descriptor with SOG-Net for long-range interactions | Integrates Cartesian atomic cluster expansion with sum-of-Gaussians neural network. |
| [Euclidean Fast Attention](https://doi.org/10.1038/s42256-026-01195-y) (Nat. Mach. Intell., 2026) | Linear-scaling attention mechanism for global atomic representations | Introduces Euclidean rotary positional encoding with spherical integration. |
| [CHGNet](https://doi.org/10.1038/s42256-023-00716-3) (Nat. Mach. Intell., 2023) | Charge-informed graph neural network with magnetic moments | Pretrained universal neural network potential that explicitly incorporates magnetic moments. |
| [M3GNet](https://doi.org/10.1038/s43588-022-00349-3) (Nat. Comput. Sci., 2022) | Universal graph deep learning IAP with three-body interactions | Graph neural network with explicit three-body interactions trained on Materials Project data. |
| [Incorporating long-range physics](https://doi.org/10.1063/1.5128375) (J. Chem. Phys., 2019) | Introduces nonlocal representations for long-range electrostatics | Proposes O(3)-equivariant nonlocal features with electrostatic-like asymptotic behavior. |

</details>

<details><summary>Polarization, Multipoles, and Electric Response</summary>

| Resource | Why it matters | Summary |
|---|---|---|
| [Machine learning interatomic potential can infer electrical response](https://www.nature.com/articles/s41524-025-01911-z) (npj Comput. Mater., 2025) | Shows that LES-style MLIPs can infer Born effective charges and response properties | Extracts polarization and BEC tensors from LES trained only on energies and forces. |
| [Foundation MLIP with polarizable long-range](https://doi.org/10.1038/s41467-025-65496-3) (Nat. Commun., 2025) | Foundation model integrating polarizable long-range physics with equivariant GNN | Uses polarizable charge equilibration optimizing electrostatic energies directly. |
| [ANI-2X/AMOEBA](https://doi.org/10.1039/d2sc04815a) (Chem. Sci., 2023) | Hybrid DNN/polarizable potential route for biomolecular simulations | Couples ANI-2X solute interactions with AMOEBA polarizable solvent/environment. |
| [Multipolar electrostatic kriging](https://doi.org/10.1021/acs.jctc.6b00457) (J. Chem. Theory Comput., 2016) | Learns geometry-dependent atomic multipoles for polarizable electrostatics | Uses kriging to predict QTAIM atomic multipoles for all natural amino acids. |
| [SchNetPack](https://doi.org/10.1021/acs.jcim.9b00181) (J. Chem. Inf. Model., 2019) | Atomistic ML toolkit with modules for atomistic properties | SchNetPack framework and the 2.0 rewrite provide extensible tooling for MLFF workflows. |
| [FENNIX-OP1](https://doi.org/10.1039/D3SC02581K) (Chem. Sci., 2023) | Force-field-enhanced equivariant NNP with learned atom-in-molecule properties | Uses ML charges and atomic volumes to parameterize charge-penetration electrostatics and Tkatchenko-Scheffler dispersion; validated on water, alanine dipeptide, and gas-phase protein dynamics. |
| [FeNNol / FeNNix](https://doi.org/10.1063/5.0217688) (J. Chem. Phys., 2024) | Force-field-enhanced NNP direction | Modular JAX library for building force-field-enhanced NNPs. |

</details>

<details><summary>Dispersion and Noncovalent Interactions</summary>

| Resource | Direction | Code / Data |
|---|---|---|
| [DFT-D3](https://www.chemie.uni-bonn.de/grimme/de/software/dft-d3) | Empirical dispersion correction often paired with MLFFs | [dftd3/simple-dftd3](https://github.com/dftd3/simple-dftd3), [tad-dftd3](https://github.com/tad-mctc/tad-dftd3) |
| [DFT-D4](https://www.chemie.uni-bonn.de/grimme/de/software/dft-d4) | Charge-dependent dispersion correction | [dftd4/dftd4](https://github.com/dftd4/dftd4) |
| [ANIPBE0-MLXDM](https://doi.org/10.1039/D2DD00150K) (Digital Discovery, 2023) | ANI-style NNP with ML-predicted XDM long-range dispersion | Learns environment-dependent C6/C8/C10 coefficients and improves DES370K intermolecular energies against CCSD(T). |
| [MBD](https://doi.org/10.1103/PhysRevLett.108.236402) (Phys. Rev. Lett., 2012) | Many-body dispersion method with self-consistent screening | Accurate treatment of frequency-dependent polarizability and many-body vdW energy. |
| [vdW in water](https://doi.org/10.1073/pnas.1602375113) (PNAS, 2016) | Demonstrates essential role of vdW forces in water properties | Shows that vdW interactions are crucial for water's density maximum. |
| [SO3LR](https://doi.org/10.1021/jacs.4c14713) (J. Am. Chem. Soc., 2025) | Combines SO3krates NN with universal pairwise force fields | Integrates semilocal SO3krates with ZBL repulsion, electrostatics, and universal vdW dispersion. |

</details>

---

### 🧪 Datasets (Long-Range)

| Dataset | Long-range relevance | Link |
|---|---|---|
| **OC25** | 7.8M+ solid-liquid interface structures with explicit solvents and ions; critical for electrolyte effects and long-range electrostatics at charged interfaces | [arXiv](https://arxiv.org/abs/2509.17862), [data](https://huggingface.co/facebook/OC25) |
| **OMC25** | 27M+ molecular crystal structures with PBE+D3 dispersion correction; diverse intermolecular interactions | [Sci. Data 2026](https://doi.org/10.1038/s41597-026-06628-2), [data](https://huggingface.co/datasets/facebook/OMC25) |
| **BioFragment Database** | Comprehensive database of noncovalent interactions in biological systems | [paper](https://doi.org/10.1063/1.4974896) |
| **DES370K** | Large noncovalent interaction dataset with 370K dimers | [paper](https://doi.org/10.1038/s41597-021-00833-x), [data](https://zenodo.org/record/4910158) |
| **SPICE** | Molecular dimers, solvated fragments, ions; useful for electrostatics and dispersion | [paper](https://doi.org/10.1038/s41597-022-01882-6), [code/data](https://github.com/openmm/spice-dataset) |
| **S66 / S66x8** | Classic benchmark for noncovalent interactions | [paper](https://doi.org/10.1021/ct2002946) |
| **QM7-X** | Off-equilibrium molecules with quantum properties, forces, dipoles | [paper](https://doi.org/10.1038/s41597-020-0473-z) |
| **QMugs** | Drug-like conformers with quantum properties | [paper](https://doi.org/10.1038/s41597-022-01390-7) |

---

### 🏆 Benchmarks (Long-Range)

| Benchmark | Description | Links |
|---|---|---|
| **MLIP Arena v1** | Benchmark platform evaluating MLIPs on physics awareness (PECs, EOS), chemical reactivity, and thermodynamic properties | [arXiv v1](https://arxiv.org/abs/2509.20630v1), [code](https://github.com/atomind-ai/mlip-arena), [leaderboard](https://huggingface.co/spaces/atomind/mlip-arena) |
| **MLIP Arena v2** | Extended version with MD stability under extreme conditions, distribution shift robustness, and extended case studies | [NeurIPS 2025](https://neurips.cc/virtual/2025/poster/121648), [arXiv v2](https://arxiv.org/abs/2509.20630v2) |

---
## 🔥 Reactive Chemistry

---

### 📖 Reviews and Perspectives (Reactive)

This list prioritizes review/perspective papers that are useful for **equivariant MLFFs for reactions**: reactive MLIP architecture, reaction-path/TS data, active learning, reactive dynamics, catalysis, and electrochemical reactivity.

| Resource | Focus | Summary |
|---|---|---|
| [Reactive machine learning interatomic potentials for chemistry and materials science](https://doi.org/10.1021/acs.chemrev.5c00728) (Chem. Rev., 2026) | Core reactive MLIP review with explicit architecture/data-acquisition framing | Especially relevant to this repo: descriptor-based models to equivariant GNNs, active learning for transition states and reaction paths, pretrained/reactive MLIP outlook. |
| [Machine learning of reactive potentials](https://doi.org/10.1146/annurev-physchem-062123-024417) (Annu. Rev. Phys. Chem., 2024) | Comprehensive review of ML potentials for reactive chemistry | Covers reactive data generation, active learning, transition state search, and applications in combustion and catalysis. |
| [The evolution of machine learning potentials for molecules, reactions and materials](https://doi.org/10.1039/D5CS00104H) (Chem. Soc. Rev., 2025) | Broad MLP review with dedicated coverage of reactions and universal potentials | Useful bridge between molecular reaction PESs, equivariant architectures, and material/catalysis applications. |
| [Neural network potential energy surfaces for small molecules and reactions](https://doi.org/10.1021/acs.chemrev.0c00665) (Chem. Rev., 2021) | Review of NN PES construction for small molecules and reaction dynamics | Strong background for high-accuracy reactive PES fitting, symmetry, sampling, observables, and quantum/classical dynamics. |
| [Machine learning for chemical reactions](https://doi.org/10.1021/acs.chemrev.1c00033) (Chem. Rev., 2021) | Broad review of ML across chemical reaction problems | Adjacent to MLFF but valuable for reaction dynamics, reactive networks, and how ML connects simulation with reaction planning/experiments. |
| [Machine learning force fields](https://doi.org/10.1021/acs.chemrev.0c01111) (Chem. Rev., 2021) | Broad MLFF review; useful background for reactive MLIPs | Comprehensive overview of MLFF methods, training strategies, and applications. |
| [Neural network potentials for chemistry: concepts, applications and prospects](https://pubs.rsc.org/en/content/articlelanding/2023/dd/d2dd00102k) (Digital Discovery, 2023) | Chemistry-facing NNP review and PES-building workflow | Good entry point for PES construction, transfer learning, spectroscopy/dynamics, and practical chemistry applications. |
| [High-dimensional potential energy surfaces for molecular simulations: from empiricism to machine learning](https://doi.org/10.1088/2632-2153/ab5922) (Mach. Learn.: Sci. Technol., 2020) | Perspective on high-dimensional PESs for molecular simulation and reactions | Useful historical bridge from empirical reactive force fields and PIP/RKHS PESs to NN potentials. |
| [Machine learning for molecular simulation](https://doi.org/10.1146/annurev-physchem-042018-052331) (Annu. Rev. Phys. Chem., 2020) | ML for energies/forces, free energies, kinetics, and sampling | Helpful context for reactive MD, free-energy surfaces, kinetics extraction, and enhanced sampling workflows. |
| [Atomistic simulations for reactions and vibrational spectroscopy in the era of machine learning - Quo Vadis?](https://doi.org/10.1021/acs.jpcb.2c00212) (J. Phys. Chem. B, 2022) | Perspective on reactive atomistic simulation and ML energy functions | Useful for connecting reactive PESs, spectroscopy, long-range/multipolar physics, and ML-driven dynamics. |
| [Data generation for machine learning interatomic potentials and beyond](https://doi.org/10.1021/acs.chemrev.4c00572) (Chem. Rev., 2024) | Review of MLIP training-data design and active learning | Directly relevant to reactive MLFFs because reaction success often depends more on TS/pathway/OOD data than on force RMSE alone. |
| [Strategies for the construction of machine-learning potentials for accurate and efficient atomic-scale simulations](https://doi.org/10.1088/2632-2153/abfd96) (Mach. Learn.: Sci. Technol., 2021) | Tutorial review on MLIP data collection, training, validation, testing, and refinement | Practical guide for building task-specific reactive potentials and active-learning loops. |
| [A practical guide to machine learning interatomic potentials - status and future](https://doi.org/10.1016/j.cossms.2025.101214) (Curr. Opin. Solid State Mater. Sci., 2025) | Practical MLIP user guide and status/future overview | Useful for deciding when to fine-tune a pretrained potential versus building a reactive dataset from scratch. |
| [Machine learning approaches for transition state prediction](https://doi.org/10.1016/j.checat.2025.101458) (Chem Catalysis, 2025) | Review of ML-assisted TS prediction and search | Adjacent but important for reactive MLFF workflows; covers modern equivariant/generative TS models and validation challenges. |
| [The potential of neural network potentials](https://doi.org/10.1021/acsphyschemau.4c00004) (ACS Phys. Chem. Au, 2024) | Perspective on the impact of equivariant NNPs in physical chemistry | Good concise motivation for why equivariant NNPs change feasible reaction and molecular simulation scales. |
| [Advancing molecular simulation with equivariant interatomic potentials](https://doi.org/10.1038/s42254-023-00615-x) (Nat. Rev. Phys., 2023) | Short perspective on equivariant interatomic potentials | Useful for the symmetry/equivariance rationale behind NequIP, Allegro, MACE-style reactive MLFFs. |
| [Recent advances and outstanding challenges for machine learning interatomic potentials](https://doi.org/10.1038/s43588-023-00561-9) (Nat. Comput. Sci., 2023) | Status/challenges perspective for modern MLIPs | Concise overview of graph/equivariant MLIPs, transferability, data, and benchmark limitations. |
| [Machine learning interatomic potentials at the centennial crossroads of quantum mechanics](https://doi.org/10.1038/s43588-025-00930-6) (Nat. Comput. Sci., 2025) | Perspective on MLIPs in the broader quantum-chemistry landscape | Useful for positioning pretrained/foundation MLIPs and reactive quantum-chemistry workflows. Summary entry not yet added. |
| [Extending machine learning beyond interatomic potentials for predicting molecular properties](https://doi.org/10.1038/s41570-022-00416-3) (Nat. Rev. Chem., 2022) | Review of learned charges, dipoles, spin/electron densities, bonding, and Hamiltonians | Important background for reactive systems where charge, spin, radical character, and bond order matter. |
| [Machine learning interatomic potentials for catalysis](https://doi.org/10.1002/chem.202401148) (Chem. Eur. J., 2024) | Review of MLIP applications and best practices for catalytic systems | Good catalysis-specific complement for surface reactions, CO2 reduction, water splitting, and adsorbate dynamics. Summary entry not yet added. |
| [Machine learning potentials for heterogeneous catalysis](https://doi.org/10.1021/acscatal.4c06717) (ACS Catal., 2025) | Perspective on MLPs for heterogeneous catalysis | Focuses on atomistic simulation of catalytic mechanisms and dynamic interfaces with near-DFT accuracy. |
| [Application of machine learning interatomic potentials in heterogeneous catalysis](https://doi.org/10.1016/j.jcat.2025.116202) (J. Catal., 2025) | Review of MLIPs across thermal, electro-, and photocatalysis | Useful application-focused survey for active sites, surface reconstruction, solid-liquid interfaces, transferability, and nonlocal-interaction limitations. |
| [The future of foundation machine learning potentials and DFT in homogeneous catalysis: competition or synergy?](https://doi.org/10.1002/chem.71022) (Chem. Eur. J., 2026) | Perspective on foundation MLIPs for homogeneous and organometallic catalysis | Very relevant to reaction workflows with ligands, oxidation states, TS exploration, uncertainty, solvation, open-shell, and multireference edge cases. |
| [Challenges and opportunities of pretrained machine learning interatomic potentials in heterogeneous catalysis](https://doi.org/10.1021/acscatal.5c08945) (ACS Catal., 2026) | Perspective on pretrained/foundation MLIPs for catalysis | Useful for assessing zero-shot/fine-tuned MLIPs on reactive surface chemistry and standardized benchmarks. |
| [Machine learning force fields in electrochemistry: from fundamentals to applications](https://doi.org/10.1021/acsnano.5c05553) (ACS Nano, 2025) | Review of MLFF foundations and electrochemical applications | Strong fit for electrolyte/electrode reactions, ionics, free-energy landscapes, and electrochemical reaction thermodynamics/kinetics. |
| [Neural network reactive force field for C/H/N/O systems](https://doi.org/10.1021/acs.jpca.0c05992) (J. Phys. Chem. A, 2020) | Early neural network reactive force-field reference for CHNO chemistry | Demonstrates feasibility of NN-based reactive potentials for organic systems. |

---

### 🔬 Models and Methods (Reactive)

<details><summary>General Reactive ML Potentials</summary>

| Model | Chemistry scope | Summary |
|---|---|---|
| [ANI-1xnr](https://github.com/atomistic-ml/ani-1xnr) (Nat. Chem., 2024) | CHNO condensed-phase reactive chemistry | Validated on combustion, carbon nucleation, graphene ring formation, biofuel additives, glycine formation. |
| [AIMNet2-rxn](https://doi.org/10.26434/chemrxiv-2025-hpdmg) (ChemRxiv, 2025) | H/C/N/O closed-shell organic reaction modeling | Designed for TS, NEB, IRC, and reaction-coordinate accuracy. [Model](https://huggingface.co/isayevlab/aimnet2-rxn) |
| [AIMNet2-NSE](https://github.com/isayevlab/aimnetcentral) | Open-shell / radical chemistry | Current AIMNetCentral model family includes spin/charge-aware variants. |
| [AIMNet2-Pd](https://doi.org/10.26434/chemrxiv-2025-n36r6) (ChemRxiv, 2025) | Pd cross-coupling reactions | Targets oxidative addition, transmetalation, reductive elimination, and catalyst screening. |
| [NewtonNet](https://github.com/THGLab/NewtonNet) (Nat. Commun., 2024) | Organic TS optimization with ML Hessians | Differentiable model used for analytical Hessian workflows. |

</details>

<details><summary>Equivariant MLIPs for Reactive Systems</summary>

| Model | Application | Summary |
|---|---|---|
| [MACE for organometallic TS](https://doi.org/10.1021/acs.jctc.4c00500) (J. Chem. Theory Comput., 2024) | Organometallic transition states and ligand effects | Demonstrates MACE's capability for modeling transition metal catalysis. |
| [MACE for drug BDE prediction](https://doi.org/10.1021/acs.jctc.4c00294) (J. Chem. Theory Comput., 2024) | Bond dissociation energies in drug-like molecules | Shows MACE can predict bond breaking energies relevant to drug metabolism. |
| [MACE for liquid electrolytes](https://doi.org/10.1021/acs.jctc.4c01307) (J. Chem. Theory Comput., 2025) | Transferability in reactive liquid electrolyte systems | Evaluates MACE transferability for electrochemical systems. |
| [NequIP for Diels-Alder dynamics](https://doi.org/10.1039/D2CP02978B) (Phys. Chem. Chem. Phys., 2022) | Diels-Alder reaction dynamics | Early demonstration of equivariant NNP for organic reaction dynamics. |
| [Allegro for methane activation](https://doi.org/10.1021/acs.jpclett.4c00562) (J. Phys. Chem. Lett., 2024) | Methane C-H activation on Ni(111) surface | Shows Allegro's capability for surface catalysis reactions. |
| [Allegro for photocatalytic CO2](https://doi.org/10.1021/acs.jpcc.4c00437) (J. Phys. Chem. C, 2024) | CuPt/TiO2 photocatalytic CO2 reduction | Demonstrates Allegro for complex photocatalytic systems. |
| [Dandelion with NequIP](https://doi.org/10.1002/advs.202404369) (Adv. Sci., 2025) | Reaction sampling and mechanism discovery | Combines NequIP with enhanced sampling for reaction discovery. |

</details>

<details><summary>Active Learning and Workflow Tools</summary>

| Tool / Paper | Role in reactive MLFF workflows | Summary |
|---|---|---|
| [Active learning metadynamics](https://doi.org/10.1039/D5DD00271K) (Digital Discovery, 2026) | Combines active learning with metadynamics for reactive MLIP training | Efficient exploration of reactive pathways with uncertainty-driven sampling. |
| [Force-free molecular dynamics through autoregressive equivariant networks](https://doi.org/10.1038/s42256-026-01227-7) (Nat. Mach. Intell., 2026) | Equivariant trajectory forecasting with TrajCast | Not an energy-force MLIP, but relevant as a force-free route for long-timescale sampling and future reactive trajectory generation. |
| [NeuralNEB](https://gitlab.com/matschreiner/neuralneb) | Uses ML potentials for NEB path search on Transition1x-style reactions | PaiNN + Transition1x for fast NEB reaction paths. |
| [Sella](https://github.com/zadorlab/sella) | ASE transition-state optimizer | Integrates with ML calculators and Hessians. |
| [PySisyphus](https://github.com/eljost/pysisyphus) | Reaction path, IRC, and TS optimization framework | Supported by AIMNetCentral extras. |
| [QuAcc](https://github.com/Quantum-Accelerators/quacc) | High-throughput atomistic workflows | Including TS / IRC recipes. |
| [ASE NEB](https://wiki.fysik.dtu.dk/ase/ase/neb.html) | Standard Python NEB interface | For ML and QM calculators. |
| [DeepMD-kit](https://github.com/deepmodeling/deepmd-kit) | Production MLIP training and MD | Often used with DP-GEN for reactive active-learning workflows. |
| [DP-GEN](https://github.com/deepmodeling/dpgen) | Concurrent learning / active-learning workflow | For DP models. |

</details>

<details><summary>Classical Reactive Force Fields (Reference)</summary>

| Method | Summary |
|---|---|
| [ReaxFF for hydrocarbon oxidation](https://doi.org/10.1021/jp709896w) (J. Phys. Chem. A, 2008) | Classical reactive force field for combustion chemistry; useful baseline for ML reactive potentials. |

</details>

---

### 🧪 Datasets (Reactive)

<details><summary>Reaction Paths, Transition States, and Barriers</summary>

| Dataset | Scope | Why it matters | Links |
|---|---|---|---|
| [Transition1x](https://doi.org/10.1038/s41597-022-01870-w) (Sci. Data, 2022) | Organic CHNO reactions, NEB paths, DFT energies/forces | 9.6M DFT calculations around 10k organic reaction pathways | [GitLab](https://gitlab.com/matschreiner/Transition1x) |
| [RGD1](https://doi.org/10.1038/s41597-023-02043-z) (Sci. Data, 2023) | 176k+ organic reactions with validated TSs and barriers | Large and diverse TS/reaction-property benchmark | [GitHub](https://github.com/zhaoqy1996/RGD1), [Zenodo](https://doi.org/10.5281/zenodo.7618731) |
| [HORM](https://www.nature.com/articles/s41597-025-06350-5) (Sci. Data, 2026) | Hessians from QM9, Transition1x, and RGD1-related geometries | Enables ML Hessian and TS optimizer research | [GitHub](https://github.com/deepprinciple/HORM/releases/tag/v1.0) |
| [Grambow reaction dataset](https://doi.org/10.1038/s41597-020-0460-4) (Sci. Data, 2020) | Small organic reaction barriers and TSs | Common benchmark for barrier prediction and TS search | |
| [BH9 / barrier-height benchmarks](https://doi.org/10.1021/acs.jctc.1c00694) (J. Chem. Theory Comput., 2022) | High-accuracy barrier-height references | Useful for validating reaction energetics | |

</details>

<details><summary>Reactive Active Learning and Condensed-Phase Data</summary>

| Dataset / Model | Scope | Why it matters | Links |
|---|---|---|---|
| [ANI-1xnr](https://doi.org/10.1038/s41557-023-01427-3) (Nat. Chem., 2024) | CHNO condensed-phase nanoreactor active learning | Demonstrates broad reactive MD without system-specific retraining | [GitHub](https://github.com/atomistic-ml/ani-1xnr) |
| [ANI-1x / ANI-1ccx](https://github.com/aiqm/torchani) | Off-equilibrium organic conformations | Useful baseline, but not sufficient alone for transition-state regions | [GitHub](https://github.com/aiqm/torchani) |
| [Open Catalyst Project](https://github.com/FAIR-Chem/fairchem) | Adsorbate-catalyst structures and relaxations | Surface reaction / catalysis-adjacent MLIP ecosystem | [GitHub](https://github.com/FAIR-Chem/fairchem) |
| [OMol25](https://arxiv.org/abs/2505.08762) (arXiv, 2025) | Open molecular dataset and models for chemical space | Useful large-scale molecular baseline; check reaction coverage per task | |

</details>

---

### 🏆 Benchmarks (Reactive)

| Benchmark | Description | Links |
|---|---|---|
| **Transition1x validation set** | Held-out reaction pathways from Transition1x dataset | [GitLab](https://gitlab.com/matschreiner/Transition1x) |
| **RGD1 test set** | Held-out reactions with validated transition states and barriers | [GitHub](https://github.com/zhaoqy1996/RGD1) |
| **HORM Hessian benchmark** | Molecular Hessian accuracy for reactive geometries | [GitHub](https://github.com/deepprinciple/HORM) |
| **Barrier height benchmarks** | BH9 and related high-accuracy barrier references | Various sources |

---


## ⚡ Constant-Potential Electrochemistry

Constant-potential electrochemical MLFFs sit at the intersection of long-range electrostatics, reactive chemistry, and electrode-reservoir thermodynamics. This section prioritizes methods that go beyond fixed-charge or fixed-field simulations by allowing electron number, interfacial charge, Fermi level/work function, or grand potential to depend on the applied potential during MD or enhanced sampling.

---

### 📖 Foundations and Reviews (Constant Potential)

| Resource | Role | Summary |
|---|---|---|
| [Machine learning force fields in electrochemistry: from fundamentals to applications](https://doi.org/10.1021/acsnano.5c05553) (ACS Nano, 2025) | Broad electrochemistry MLFF review | Good entry point for electrolyte/electrode interfaces, ion transport, free energies, and electrochemical reaction barriers. |
| [Grand Canonical Quantum Mechanics with Applications to Mechanisms and Rates for Electrocatalysis](https://doi.org/10.1007/s11244-023-01794-8) (Top. Catal., 2023) | GC-QM / GCP-K reference framework | Useful baseline for what constant-potential reaction energetics mean before adding an ML surrogate. |
| [Atomistic learning in the electronically grand-canonical ensemble](https://doi.org/10.1038/s41524-023-01007-6) (npj Comput. Mater., 2023) | Early electronically grand-canonical atomistic learning | Dual-learning scheme predicts charge and energy across potentials; includes uncertainty and saddle-point acceleration. [Code](https://bitbucket.org/andrewpeterson/amp/) |

---

### 🔬 Models and Methods (Constant Potential)

<details><summary>Grand-Canonical and Variable-Electron MLFFs</summary>

| Model | Constant-potential ingredient | Application and caveat |
|---|---|---|
| [CP-MLFF / MACE](https://doi.org/10.1021/acs.jctc.5c00784) (J. Chem. Theory Comput., 2025) | Equivariant GNN takes electron number as input and predicts forces plus Fermi level; implemented as a MACE extension | CO2RR step on Ni-N-C; especially close to the GC-QM/GCP-K idea for potential-dependent barriers. |
| [CPMPNN](https://doi.org/10.1021/acs.jctc.5c01381) (J. Chem. Theory Comput., 2025) | E(3)-equivariant message passing with a global excess-electron variable redistributed by multihead attention | Grand potential, forces, and work function for Cu(100) CO dimerization and Volmer chemistry; reported ~1000x GCDFT speedup. |
| [ML-enhanced grand-canonical constant-potential approach](https://doi.org/10.1038/s41467-025-58871-7) (Nat. Commun., 2025) | DP-Ne potential plus GC-HMC / path-integral sampling for electron-number fluctuations and nuclear quantum effects | HER PCET free energies; strong example of MLFF-assisted exact-GC sampling rather than only fixed-work-function snapshots. [Code](https://github.com/sxu39/GC-ConstrainedPIHMC) |
| [DPchi](https://doi.org/10.26434/chemrxiv-2025-6vcnc) (ChemRxiv, 2025) | Charge-based DP/DPLR-style model with Bader-basin centroids, neural chemical charge, and conductor response under electroneutrality | Validated on Pt(111)-water potential drops, Volmer barriers, and vibrational signatures; currently a focused benchmark rather than a universal electrocatalysis model. |
| [Constant-potential reactor / veNNP](https://doi.org/10.1021/jacsau.5c01198) (JACS Au, 2026) | Variable-electronic NNP predicts energy, forces, charges, and corrected Fermi level; coupled to modified Nose-Hoover constant-potential MD | Au-water CO2RR with cation effects; combines active learning, Ewald electrostatics, and slow-growth free-energy calculations. |
| [DP-QEq constant-potential framework](https://doi.org/10.1038/s41467-025-62824-5) (Nat. Commun., 2025) | ML short-range energy plus QEq/PME electrostatics under electrode-potential constraints | Li metal-electrolyte dendrite nucleation; best viewed as a battery-interface ConstP MLFF/QEq framework. [Code](https://github.com/sxu39/DP-QEq) |
| [Constant-potential MLMD for Cu/MoS2](https://doi.org/10.1021/acs.jpcc.4c08188) (J. Phys. Chem. C, 2025) | Potential-regulated MLMD for interfacial cluster formation | Useful application paper, but check whether the workflow samples a full GCE with Fermi-level fluctuations or uses fixed-potential/charged training states. |

</details>

---

### 🧩 Adjacent and Cautionary Methods

| Resource | Why it is related | Classification caveat |
|---|---|---|
| [ec-MLP](https://doi.org/10.1103/48ct-3jxm) (Phys. Rev. Lett., 2025) | Hybrid representation for dielectric response at electrochemical interfaces | Very relevant for metal-water structure and potential response, but not the same as a reaction-ready electronically grand-canonical MLFF. |
| [RAZOR](https://doi.org/10.1103/lm64-m3bn) (Phys. Rev. Lett. 135, 146201, 2025) | Learns energetics of electrified solid-liquid interfaces | Strong for potential-dependent interfacial energetics; not a general-purpose constant-potential reactive MD force field. |
| [PiNNwall](https://doi.org/10.1021/acs.jctc.2c01162) (J. Chem. Theory Comput., 2023) | ML-assisted heterogeneous electrode wall model | Closer to classical constant-potential electrode / double-layer modeling than DFT-accuracy reactive MLFF. |
| [Machine learning interatomic potential can infer electrical response](https://doi.org/10.1038/s41524-025-01911-z) (npj Comput. Mater., 2025) | LES-style MLIP can infer polarization and Born effective charges | Important electric-field response work, but finite-field dielectric response is not automatically constant-electrode-potential sampling. |

---

### 🧪 Codes, Data, and Reproducibility

| Resource | Use | Summary |
|---|---|---|
| [Amp](https://bitbucket.org/andrewpeterson/amp/) | Original electronically grand-canonical atomistic-learning implementation | Paper reports sample scripts in the SI; training sets were available on request. |
| [GC-ConstrainedPIHMC](https://github.com/sxu39/GC-ConstrainedPIHMC) | Grand-canonical constrained/path-integral HMC sampling | Supports the Nat. Commun. 2025 NQE electrocatalysis workflow. |
| [DP-QEq](https://github.com/sxu39/DP-QEq) | MLFF + QEq constant-potential MD framework | Related Zenodo records provide source data, training datasets, code archive, and force-field models. [Dataset](https://doi.org/10.5281/zenodo.15776510), [Models](https://doi.org/10.5281/zenodo.15778975) |
| [DeepMD-kit](https://github.com/deepmodeling/deepmd-kit) + [DP-GEN](https://github.com/deepmodeling/dpgen) | Base training and active-learning ecosystem | Used by multiple DP-style constant-potential workflows; the constant-potential physics is usually a paper-specific extension. |
| [MACE](https://github.com/ACEsuit/mace) | Base equivariant MLIP framework | CP-MLFF shows how to add electron-number conditioning and Fermi-level targets; check whether the CP branch/code is available for your use case. |

---

## 🛠️ Software Ecosystem

| Project | Use in MLFF workflows |
|---|---|
| [AIMNetCentral](https://github.com/isayevlab/aimnetcentral) | AIMNet2 calculators, reaction models, ASE/PySisyphus/Sella extras, Hessian support |
| [TorchANI](https://github.com/aiqm/torchani) | ANI model family implementation and baseline molecular NNPs |
| [DeepMD-kit](https://github.com/deepmodeling/deepmd-kit) | Production MLIP training and MD; works with active learning ecosystems |
| [DP-GEN](https://github.com/deepmodeling/dpgen) | Concurrent learning / active-learning workflow for DP models |
| [GC-ConstrainedPIHMC](https://github.com/sxu39/GC-ConstrainedPIHMC) | Grand-canonical constrained/path-integral HMC sampling for constant-potential electrocatalysis |
| [DP-QEq](https://github.com/sxu39/DP-QEq) | MLFF + QEq constant-potential MD for Li metal/electrolyte interfaces |
| [MACE](https://github.com/ACEsuit/mace) | Equivariant MLIP framework for custom datasets |
| [Amp](https://bitbucket.org/andrewpeterson/amp/) | Atomistic ML package used for electronically grand-canonical learning examples |
| [NequIP](https://github.com/mir-group/nequip) | Equivariant GNN MLIP framework |
| [Allegro](https://github.com/mir-group/allegro) | Scalable equivariant MLIP architecture |
| [SchNetPack](https://github.com/atomistic-machine-learning/schnetpack) | Atomistic ML toolkit with MD and property prediction workflows |
| [TorchMD-Net](https://github.com/torchmd/torchmd-net) | Molecular ML potentials and simulation tooling |
| [ASE](https://gitlab.com/ase/ase) | NEB, calculators, optimizers, MD, file IO |
| [Sella](https://github.com/zadorlab/sella) | Transition-state optimization |
| [PySisyphus](https://github.com/eljost/pysisyphus) | IRC, TS optimization, reaction paths |
| [KinBot](https://github.com/zadorlab/KinBot) | Automated gas-phase reaction discovery and TS guess generation |
| [FAIR-Chem](https://github.com/FAIR-Chem/fairchem) | Open Catalyst and atomistic ML models for catalysis/materials |

---

## 🧠 Reading Map

### If you are new to long-range interactions:

1. Start with **PhysNet** and **SpookyNet** to see how molecular MLFFs incorporate charges, dipoles, and dispersion
2. Read **DPLR** for periodic long-range electrostatics with Wannier centers
3. Read **LES** and **SOG-Net** for current reciprocal-space / latent-variable strategies
4. Test on at least one charged, polar, interfacial, or noncovalent dataset

### If you are new to reactive chemistry:

1. Start with **ANI-1xnr** to see how active learning captures condensed-phase reactivity
2. Read **AIMNet2-rxn** for transition-state and reaction-path modeling
3. Explore **Transition1x** and **RGD1** datasets to understand reactive data requirements
4. Test on held-out reactions and verify barrier accuracy, not just force RMSE

### If you are new to constant-potential electrochemistry:

1. Start with **GC-QM/GCP-K** and **Atomistic learning in the electronically GCE** to understand why the energy depends on both nuclear positions and electrode conditions
2. Compare **CP-MLFF/MACE** and **CPMPNN** for two modern equivariant routes to variable-electron constant-potential MLFFs
3. Read **DP-Ne/GC-PIHMC** and **constant-potential reactor/veNNP** for sampling-heavy electrochemical reaction workflows
4. Treat **ec-MLP**, **RAZOR**, **PiNNwall**, and electrical-response MLIPs as adjacent tools unless they explicitly sample the desired grand-canonical ensemble

### If you are building a model:

**For long-range:**
1. Decide whether the system needs explicit asymptotic physics, learned nonlocal communication, or a hybrid
2. Check if required labels are available: charges, dipoles, MLWCs, dielectric response, or only energy/force
3. Verify extensivity, charge neutrality, PBC convention, force consistency, and energy conservation
4. Compare against a strong short-range baseline plus D3/D4 before claiming long-range gains

**For reactive:**
1. Ensure training distribution covers bond-breaking/forming geometries
2. Check element/charge/spin scope: does the model support radicals, ions, metals needed by your system?
3. Validate barrier accuracy and reaction energies against QM on held-out reactions
4. Verify reactant/product graph matching and IRC/NEB connectivity, not only force RMSE
5. Use ensembles or active-learning indicators for out-of-domain structures

**For constant-potential electrochemistry:**
1. Decide whether the controlled variable is applied potential, electron chemical potential, work function, total electron number, or electrode charge
2. Train and validate every coupled target used by the sampler: forces, grand potential/energy, Fermi level/work function, total charge, and charge redistribution
3. Keep the potential reference explicit: SHE/RHE/vacuum/electrolyte reference, PZC, implicit solvent, and countercharge choices
4. Test whether electron number or charge can fluctuate correctly at fixed potential, instead of merely interpolating between fixed-charge snapshots
5. Validate capacitance, potential drops, finite-size behavior, and reaction barriers over the target potential window

---

## ✅ Validation Checklist

### Long-Range Systems

- [ ] Test on charged, polar, or interfacial systems beyond training distribution
- [ ] Verify correct asymptotic electrostatic behavior (1/r decay)
- [ ] Check energy conservation in MD simulations
- [ ] Compare against short-range baseline + D3/D4 correction
- [ ] Validate on noncovalent interaction benchmarks (S66, DES370K)
- [ ] Test finite-size effects and PBC convergence

### Reactive Systems

- [ ] Coverage: are bond-breaking/forming geometries in the training distribution?
- [ ] Element/charge/spin scope: does the model support radicals, ions, metals, solvents needed?
- [ ] Barrier accuracy: compare activation energies and reaction energies against QM on held-out reactions
- [ ] Path identity: verify reactant/product graph matching and IRC/NEB connectivity
- [ ] Conservation: confirm energy-conserving forces for MD and stable trajectories
- [ ] Uncertainty: use ensembles or active-learning indicators for out-of-domain structures
- [ ] Negative controls: test near-equilibrium-only models to quantify the gain from reactive data
- [ ] Reoptimization: if ML finds a TS, reoptimize or single-point check with QM for critical claims

### Constant-Potential Electrochemistry

- [ ] Ensemble definition: is the simulation constant-potential / electronically grand-canonical, or only fixed charge / fixed field?
- [ ] Potential reference: are SHE/RHE/vacuum/electrolyte offsets, PZC, pH convention, and countercharge treatment stated?
- [ ] Coupled observables: are forces, grand potential/energy, Fermi level/work function, and charge/electron number all validated?
- [ ] Charge response: does the model reproduce capacitance, potential drop, and charge redistribution against GCDFT or another reference?
- [ ] Sampling: are solvent/ion configurations and reaction coordinates sampled long enough for barrier convergence?
- [ ] Finite-size effects: are slab size, water thickness, electrolyte concentration, and PBC neutrality tested?
- [ ] Scope: is the model only valid for one electrode/electrolyte/potential window, or transferable to new interfaces?

---

## Contributing

We welcome contributions! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and submit a pull request.

Preferred entry format:

```markdown
- [Paper Title](paper-url) (Venue, Year) - one sentence on relevance. [Code](code-url) [Data](data-url)
```

---

## Cite This Repository

If you find this repository useful, please consider citing:

```bibtex
@misc{awesome_ml_force_fields_2026,
  title        = {Awesome Machine Learning Force Fields: Long-Range Interactions, Reactive Chemistry, and Constant-Potential Electrochemistry},
  author       = {ZeHeru and contributors},
  year         = {2026},
  howpublished = {\url{https://github.com/ZeHeru/Awesome-ML-Force-Field-Long-Range}}
}
```

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

This list is inspired by the open-source awesome-list culture. Thanks to researchers who release papers, datasets, trained models, and reproducible code for the MLFF community.
