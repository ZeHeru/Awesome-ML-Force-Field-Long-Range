<h1 align="center">🎉 Awesome-ML-Force-Field-Long-Range 🔥</h1>

---

<p align="center">
<img width="768px" alt="Awesome ML Force Field Long Range" src="assets/logoGithub.svg">
</p>

<p align="center">
<img src="https://img.shields.io/badge/Awesome-Survey-8A2BE2" alt="Awesome Survey">
<img src="https://img.shields.io/badge/Focus-Long--Range%20Interactions-blue" alt="Long Range Interactions">
<img src="https://img.shields.io/badge/Topics-Electrostatics%20%7C%20Dispersion%20%7C%20Polarization-4BC88C" alt="Topics">
<br>
<img src="https://img.shields.io/badge/Update%20🔥-2026.05.01-red" alt="Update">
<img src="https://img.shields.io/badge/PRs-Welcome-orange" alt="PRs Welcome">
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

<details><summary>🎁 >>>>>>>> [English Introduction] <<<<<<<<<< </summary>

> This repository is a focused navigation map for **long-range interactions in machine learning force fields / machine learning interatomic potentials (MLFFs / MLIPs)**.
>
> It tracks papers, code, datasets, and implementation notes for models that go beyond the usual short-range locality assumption.
>
> The list is organized around four recurring design choices:
>
> 🌑 **Explicit electrostatics**: charges, dipoles, charge equilibration, polarization, Ewald/PME, and Wannier-center based models.
>
> 🌒 **Learned global communication**: reciprocal-space message passing, latent Ewald variables, Fourier convolution, global nodes, and nonlocal descriptors.
>
> 🌓 **Dispersion and van der Waals**: D3/D4/MBD-style corrections and datasets for noncovalent interaction learning.
>
> 🎉 Contributions are welcome. If a long-range MLFF paper, repository, or benchmark is missing, please submit a PR.

</details>

<details><summary>🏆 >>>>>>>> [🧡中文简要介绍💜] <<<<<<<<<< </summary>

<br>

> 本项目专门整理👍**机器学习力场 / 机器学习原子间势中的长程相互作用**👏相关工作。
>
> 这里关注的问题不是普通 MLIP 大而全导航，而是聚焦：短程 cutoff 假设什么时候失效、如何显式或隐式补上长程物理、哪些代码可以直接用于模拟。
>
> 仓库按照以下主线整理：
>
> 🌑 **长程静电**：原子电荷、偶极、QEq、极化、Ewald/PME、Wannier center、Born effective charge。
>
> 🌒 **全局通信机制**：reciprocal-space message passing、Latent Ewald、Fourier convolution、global/relay node、nonlocal descriptor。
>
> 🌓 **色散与范德华**：D3/D4/MBD 修正、非共价相互作用数据集、短程模型 + 显式色散的混合路线。
>
> 🎉 欢迎补充遗漏论文、代码、数据集与复现实验。这个列表会持续更新。

</details>

---

<p align="center">
🍦 Long-range physics for practical atomistic machine learning. 🍦
<br>
<br>
<img src="assets/pipeline.svg" width="768px" alt="Long-range MLFF pipeline"/>
</p>

---

## Introduction

Most modern MLFFs decompose the energy into local atomic environments and use a finite cutoff. This works surprisingly well for many bulk and near-equilibrium systems, but it can fail for charged molecules, polar liquids, interfaces, ionic materials, ferroelectrics, heterogeneous catalysis, and dilute electrolyte systems where electrostatics, dispersion, or polarization remain relevant far beyond the cutoff.

This repository collects methods that explicitly address this gap.

### ✨You are welcome to provide work related to long-range ML force fields.✨

If you discover a missing paper, dataset, benchmark, or codebase, please open a PR or issue. The most useful additions include a stable link, a one-sentence motivation, and code availability.

### 🍔 Highlights

- **Electrostatics-aware MLFFs**: PhysNet, 4G-HDNNP, AIMNet-NSE, CENT, SCFNN, and related models show how charges, dipoles, QEq, and self-consistent response can be learned instead of ignored.
- **Periodic long-range routes**: DPLR, DeepWannier, LES, and LES augmentation connect MLIPs with Wannier centers, latent Ewald variables, and reciprocal-space summation.
- **Learned global communication**: EwaldMP, SOG-Net, CACE-SOG, and Euclidean Fast Attention explore nonlocal message passing, Fourier kernels, and attention for interactions beyond a fixed cutoff.
- **Evaluation pressure tests**: MLIP Arena, OC25, OMC25, SPICE, DES370K, and interfacial/ferroelectric benchmarks help distinguish true long-range modeling from short-range fitting artifacts.

### 🕑 Timeline

| Period | Milestone | Representative entries |
|---|---|---|
| 2015-2018 | Charge-aware descriptors and early neural charge assignment | CENT, HIPNN Charge |
| 2019-2021 | Explicit electrostatics, nonlocal charge transfer, and long-range MLIP reviews mature | PhysNet, 4G-HDNNP, AIMNet-NSE, SpookyNet, Grisafi-Ceriotti nonlocal features |
| 2022-2024 | Periodic electrostatics, Wannier response, and force-field-enhanced NNP software become practical | DPLR, SCFNN, FeNNol/FeNNix |
| 2025 | Latent/global long-range layers and large benchmarks accelerate | LES, SOG-Net, SO3LR, BAMBOO, MLIP Arena, OC25 |
| 2026 | Standalone augmentation, CACE-SOG coupling, global attention, and molecular-crystal benchmarks expand the toolkit | LES augmentation, CACE-SOG, Euclidean Fast Attention, OMC25 |

---

## 📚 Table of Contents

- [💙 News](#-news)
- [🍔 Highlights](#-highlights)
- [🕑 Timeline](#-timeline)
- [🧭 Taxonomy](#-taxonomy)
- [📌 Core Papers and Code](#-core-papers-and-code)
- [⚡ Long-Range Electrostatics](#-long-range-electrostatics)
- [🧲 Polarization, Multipoles, and Electric Response](#-polarization-multipoles-and-electric-response)
- [🌫️ Dispersion and Noncovalent Interactions](#️-dispersion-and-noncovalent-interactions)
- [🏆 Benchmarks](#-benchmarks)
- [🧪 Datasets and Benchmarks](#-datasets-and-benchmarks)
- [📖 Reviews and Perspectives](#-reviews-and-perspectives)
- [🧠 Reading Map](#-reading-map)
- [Contributing](#contributing)
- [Cite This Repository](#cite-this-repository)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## 💙 News

**[2026/05/01] [V0.1] Initial release.**

- Created a focused navigation list for long-range interactions in MLFFs / MLIPs.
- Added first taxonomy and dataset links.
- PRs are welcome for missing methods, benchmarks, and reproducibility notes.

---

## 🧭 Taxonomy

| Family | Typical ingredients | Strength | Typical caveat |
|---|---|---|---|
| Charge / dipole learning | Atomic charges, molecular dipoles, charge constraints, QEq | Physically interpretable electrostatics | Needs charge/dipole labels or reliable constraints |
| Wannier-center / electronic-center learning | MLWCs, electronic response variables | Strong for insulating periodic systems | Requires extra electronic-structure labels |
| Ewald / PME augmentation | Explicit reciprocal-space summation | Correct asymptotic periodic electrostatics | Engineering complexity and charge neutrality details |
| Latent reciprocal variables | Hidden charges or latent fields + Ewald/Fourier layers | Can learn from energy/force only | Interpretability and transfer need validation |
| Global message passing | Ewald features, global nodes, Fourier convolution | Adds nonlocal communication to GNNs | May still need physics priors for asymptotics |
| Dispersion correction | D3/D4/MBD or learned dispersion tail | Cheap and robust for vdW | Double-counting if base model already learned it |

---

## 📌 Core Papers and Code

| Resource | Why start here | Links |
|---|---|---|
| PhysNet | Canonical molecular MLFF with learned charges, dipoles, explicit electrostatics, and dispersion. | [paper](https://doi.org/10.1021/acs.jctc.9b00181) |
| 4G-HDNNP | Introduces global charge equilibration into high-dimensional NNPs for nonlocal charge transfer. | [paper](https://doi.org/10.1038/s41467-020-20427-2) |
| DPLR | Practical periodic long-range electrostatics through Deep Potential plus learned Wannier centers. | [paper](https://doi.org/10.1063/5.0083669) |
| LES | Latent Ewald summation route that can learn long-range interactions from energy/force supervision. | [paper](https://doi.org/10.1038/s41524-025-01577-7) |
| SOG-Net | Fourier / sum-of-Gaussians global kernel for learning long-range decay tails. | [arXiv](https://arxiv.org/abs/2502.04668) |
| MLIP Arena | Open benchmark platform for testing MLIP physical soundness beyond standard error metrics. | [arXiv](https://arxiv.org/abs/2509.20630), [code](https://github.com/atomind-ai/mlip-arena), [leaderboard](https://huggingface.co/spaces/atomind/mlip-arena) |

---

## ⚡ Long-Range Electrostatics

<details><summary>Charge, Dipole, and QEq Models</summary>

| Method | Main idea |
|---|---|---|
| [PhysNet](https://doi.org/10.1021/acs.jctc.9b00181) (J. Chem. Theory Comput., 2019) | Predicts partial charges and dipoles together with energies/forces | Multitask energy/charge learning; predicted charges enter an explicit electrostatic term and dipoles are trained as observables |
| [SpookyNet](https://doi.org/10.1038/s41467-021-27504-0) (Nat. Commun., 2021) | Adds electronic degrees of freedom and nonlocal effects | Uses total charge/spin embeddings, nonlocal interactions, and analytic electrostatic/dispersion corrections to handle electronic-state ambiguity and nonlocality |
| [4G-HDNNP](https://doi.org/10.1038/s41467-020-20427-2) (Nat. Commun., 2021) | Neural atomic energy + global charge equilibration | Uses QEq over NN-predicted electronegativities; the resulting global charges feed both long-range electrostatics and short-range atomic networks |
| [AIMNet2](https://github.com/isayevlab/aimnetcentral) | Charge-aware neural potential with Ewald/DSF and D3 support in current code | No dedicated AIMNet2 note yet; related notes cover original AIMNet and AIMNet-NSE |
| [AIMNet-NSE](https://doi.org/10.1038/s41467-021-24904-0) (Nat. Commun., 2021) | Neural sum of energies approach with charge prediction | Neural spin-charge equilibration conserves total spin charges by construction, enabling one model across neutral, cationic, anionic, and spin states |
| [BAMBOO](https://doi.org/10.1038/s42256-025-01009-7) (Nat. Mach. Intell., 2025) | Electrolyte force-field framework with ML charges and liquid-electrolyte focus | Graph equivariant transformer MLFF for liquid electrolytes with semi-local, QEq electrostatic, and D3 dispersion terms plus density alignment to experiments |
| [HIPNN Charge](https://doi.org/10.1021/acs.jpclett.8b00684) (J. Phys. Chem. Lett., 2018) | Hierarchical interacting particle neural network with charge prediction | ACA uses HIP-NN to infer partial charges from molecular dipoles; the learned charges transfer to quadrupoles and larger molecules |
| [SCFNN](https://doi.org/10.1038/s41467-022-29243-2) (Nat. Commun., 2022) | Self-consistent field neural network for charge equilibration | Separates Gaussian-truncated short-range physics from long-range electric-field response; MLWFCs and forces are coupled through a self-consistent loop |
| [BpopNN](https://doi.org/10.1021/acs.jctc.0c00217) (J. Chem. Theory Comput., 2020) | Bond-order potential neural network with charge transfer | Treats DFT energy as a function of atom-based electron populations from CDFT; optimizing populations lets electronic terms adapt self-consistently |
| [CENT](https://doi.org/10.1103/PhysRevB.92.045131) (Phys. Rev. B, 2015) | Charge equilibration via neural network technique | Learns environment-dependent electronegativities via NN to predict atomic charges through charge equilibration; enables accurate description of charge transfer in ionic systems |

</details>

<details><summary>Ewald, PME, Fourier, and Reciprocal-Space Models</summary>

| Method | Main idea |
|---|---|---|
| [DPLR](https://doi.org/10.1063/5.0083669) (J. Chem. Phys., 2022) | Learns Wannier centers and evaluates long-range electrostatics with Deep Potential | Adds Gaussian charges at ionic sites and MLWC-derived electronic sites to DP; tested on water dimer/slab and NaCl phonons |
| [DeepWannier for Dielectric Response](https://doi.org/10.1103/PhysRevB.102.041121) (Phys. Rev. B, 2020) | Learns Wannier centers for dielectric properties | Learns MLWC centers with a symmetry-preserving DNN, then combines with DP to access dielectric response and spectra of insulating systems |
| [EwaldMP](https://github.com/arthurkosmala/EwaldMP) | Adds Ewald-based long-range message passing to molecular graphs | No mmd note in this repository yet. |
| [LES](https://doi.org/10.1038/s41524-025-01577-7) (npj Comput. Mater., 2025) | Learns latent variables and applies Ewald summation | Predicts latent variables from local descriptors and couples them globally through Ewald summation; benchmarks include charged/polar dimers, molten NaCl, bulk water, and water interfaces |
| [LES augmentation](https://doi.org/10.1021/acs.jctc.5c01400) (J. Chem. Theory Comput., 2026) | Standalone LES library attached to CACE, MACE, NequIP, Allegro, CHGNet, UMA | Standalone PyTorch LES module for retrofitting short-range MLIPs; can infer electrostatics, polarization, and BECs from energy/force training |
| [SOG-Net](https://arxiv.org/abs/2502.04668) (arXiv, 2025) | Learns sum-of-Gaussians long-range kernels with Fourier convolution | Learns latent variables and sum-of-Gaussians Fourier convolution kernels to cover different long-range decay tails with near-linear NUFFT-based scaling |
| [CACE-SOG](https://doi.org/10.1063/5.0303312) (J. Chem. Phys., 2026) | Couples CACE descriptor with SOG-Net for long-range interactions | Integrates Cartesian atomic cluster expansion with sum-of-Gaussians neural network to accurately learn long-range interactions with different decay rates |
| [Euclidean Fast Attention](https://doi.org/10.1038/s42256-026-01195-y) (Nat. Mach. Intell., 2026) | Linear-scaling attention mechanism for global atomic representations | Introduces Euclidean rotary positional encoding with spherical integration for rotation-invariant long-range modeling; enables MPNNs to capture non-local charge transfer and long-range electrostatics |
| [Reciprocal Space Neural Network](https://arxiv.org/abs/2211.16684) (arXiv, 2022) | Uses reciprocal-space representation to capture long-range interactions | No mmd note in this repository yet. |
| [SCFNN](https://doi.org/10.1038/s41467-022-29243-2) (Nat. Commun., 2022) | Self-consistent treatment of long-range electrostatics in neural network potentials | Separates Gaussian-truncated short-range physics from long-range electric-field response; MLWFCs and forces are coupled through a self-consistent loop |
| [Incorporating long-range physics](https://doi.org/10.1063/1.5128375) (J. Chem. Phys., 2019) | Introduces nonlocal representations for long-range electrostatics | Proposes O(3)-equivariant nonlocal features with electrostatic-like asymptotic behavior to capture long-range correlations in charged molecular dimers and dielectric response |

</details>

---

## 🧲 Polarization, Multipoles, and Electric Response

| Resource | Why it matters |
|---|---|---|
| [Machine learning interatomic potential can infer electrical response](https://www.nature.com/articles/s41524-025-01911-z) (npj Comput. Mater., 2025) | Shows that LES-style MLIPs can infer Born effective charges and response properties. | Extracts polarization and BEC tensors from LES trained only on energies and forces; applications include IR spectra, ionic conductivity, and ferroelectric hysteresis |
| [Foundation MLIP with polarizable long-range](https://doi.org/10.1038/s41467-025-65496-3) (Nat. Commun., 2025) | Foundation model integrating polarizable long-range physics with equivariant GNN | Uses polarizable charge equilibration optimizing electrostatic energies directly; trained across periodic table up to Pu for mechanical properties, ionic diffusion, ferroelectrics, and reactive dynamics |
| [ANI-2X/AMOEBA](https://doi.org/10.1039/d2sc04815a) (Chem. Sci., 2023) | Hybrid DNN/polarizable potential route for biomolecular simulations with long-range effects. | Couples ANI-2X solute interactions with AMOEBA polarizable solvent/environment and PME long-range electrostatics in Deep-HP |
| [Multipolar electrostatic kriging](https://doi.org/10.1021/acs.jctc.6b00457) (J. Chem. Theory Comput., 2016) | Learns geometry-dependent atomic multipoles for polarizable electrostatics. | Uses kriging to predict QTAIM atomic multipoles for all natural amino acids, including charged variants, and reconstruct electrostatic interaction energies |
| [SchNetPack](https://doi.org/10.1021/acs.jcim.9b00181) (J. Chem. Inf. Model., 2019) | Atomistic ML toolkit with modules for atomistic properties and extensible model components. | Toolbox notes for the original SchNetPack framework and the 2.0 rewrite with equivariant modules, PyTorch Lightning/Hydra, and MD support |
| [FeNNol / FeNNix](https://doi.org/10.1063/5.0217688) (J. Chem. Phys., 2024) | Force-field-enhanced NNP direction; useful to watch for local + long-range energy decomposition. | Modular JAX library for building force-field-enhanced NNPs, including physics modules such as Coulomb/Ewald terms and charge equilibration |

---

## 🌫️ Dispersion and Noncovalent Interactions

| Resource | Direction | Code / Data |
|---|---|---|
| [DFT-D3](https://www.chemie.uni-bonn.de/grimme/de/software/dft-d3) | Empirical dispersion correction often paired with MLFFs | [dftd3/simple-dftd3](https://github.com/dftd3/simple-dftd3), [tad-dftd3](https://github.com/tad-mctc/tad-dftd3) |
| [DFT-D4](https://www.chemie.uni-bonn.de/grimme/de/software/dft-d4) | Charge-dependent dispersion correction | [dftd4/dftd4](https://github.com/dftd4/dftd4) |
| [MBD](https://doi.org/10.1103/PhysRevLett.108.236402) (Phys. Rev. Lett., 2012) | Many-body dispersion method with self-consistent screening | Accurate treatment of frequency-dependent polarizability and many-body vdW energy beyond pairwise approximation; crucial for biomolecules and molecular crystals |
| [vdW in water](https://doi.org/10.1073/pnas.1602375113) (PNAS, 2016) | Demonstrates essential role of vdW forces in water properties | Shows that vdW interactions are crucial for water's density maximum and negative volume of melting through flexibility of HB network |
| [SO3LR](https://doi.org/10.1021/jacs.4c14713) (J. Am. Chem. Soc., 2025) | Combines SO3krates NN with universal pairwise force fields for long-range | Integrates semilocal SO3krates with ZBL repulsion, electrostatics, and universal vdW dispersion; trained on 4M structures for biomolecular simulations up to 200k atoms |
| [DES370K](https://doi.org/10.1038/s41597-021-00833-x) | Large noncovalent interaction dataset | [DES370K data](https://zenodo.org/record/4910158) |
| [S66 / S66x8](https://doi.org/10.1021/ct2002946) | Classic benchmark for noncovalent interactions | Useful for sanity checks |
| [SPICE](https://doi.org/10.1038/s41597-022-01882-6) | Drug-like molecules, dimers, solvated amino acids, ions | [OpenMM/SPICE](https://github.com/openmm/spice-dataset) |

---

## 🏆 Benchmarks

| Benchmark | Description | Links |
|---|---|---|
| **MLIP Arena v1** | Benchmark platform evaluating MLIPs on physics awareness (PECs, EOS), chemical reactivity (hydrogen combustion), and thermodynamic properties (vacancy migration, phase transitions). Focuses on physical soundness beyond error-based metrics. | [arXiv v1](https://arxiv.org/abs/2509.20630v1), [code](https://github.com/atomind-ai/mlip-arena), [leaderboard](https://huggingface.co/spaces/atomind/mlip-arena) |
| **MLIP Arena v2** | Extended version with additional benchmarks including MD stability under extreme conditions (NVT/NPT), distribution shift robustness (energy conservation, rotational equivariance), and extended case studies (CO₂ adsorption in MOFs, 2D materials stability). | [NeurIPS 2025](https://neurips.cc/virtual/2025/poster/121648), [arXiv v2](https://arxiv.org/abs/2509.20630v2), [code](https://github.com/atomind-ai/mlip-arena) |

---

## 🧪 Datasets and Benchmarks

| Dataset | Long-range relevance | Link |
|---|---|---|
| **OC25** | 7.8M+ solid-liquid interface structures with explicit solvents (water, acetonitrile, etc.) and ions; critical for understanding electrolyte effects in electrocatalysis and long-range electrostatics at charged interfaces | [arXiv](https://arxiv.org/abs/2509.17862), [data](https://huggingface.co/facebook/OC25), [models](https://huggingface.co/facebook/OC25) |
| **OMC25** | 27M+ molecular crystal structures with PBE+D3 dispersion correction; diverse intermolecular interactions (H-bonds, pi-pi stacking, van der Waals) across 12 elements and multiple space groups | [Sci. Data 2026](https://doi.org/10.1038/s41597-026-06628-2), [data](https://huggingface.co/datasets/facebook/OMC25), [models](https://huggingface.co/facebook/OMC25) |
| SPICE | Molecular dimers, solvated fragments, ions; useful for electrostatics and dispersion | [paper](https://doi.org/10.1038/s41597-022-01882-6), [code/data](https://github.com/openmm/spice-dataset) |
| DES370K | High-quality noncovalent interaction energies for dispersion / H-bond / electrostatics | [paper](https://doi.org/10.1038/s41597-021-00833-x), [data](https://zenodo.org/record/4910158) |
| QM7-X | Off-equilibrium molecules with quantum properties, forces, dipoles | [paper](https://doi.org/10.1038/s41597-020-0473-z) |
| QMugs | Drug-like conformers with quantum properties | [paper](https://doi.org/10.1038/s41597-022-01390-7) |
| Water / ions / interfaces | Critical stress test for electrostatics, dielectric response, and finite-size artifacts | See LES and DPLR benchmark papers |
| Polar crystals / ferroelectrics | Born effective charge and dielectric-response tests | See LES-BEC and related response-property work |

---

## 📖 Reviews and Perspectives

| Resource | Focus |
|---|---|---|
| [Neural network potentials for chemistry: concepts, applications and prospects](https://pubs.rsc.org/en/content/articlelanding/2023/dd/d2dd00102k) (Digital Discovery, 2023) | Comprehensive review of NN-based PESs for chemistry | Covers theoretical background, NN architectures, descriptors (predefined vs learnable), PES construction workflows, knowledge transfer, applications in spectroscopy and dynamics, and current challenges in data management and interpretability |
| [Neural network potentials: a concise overview of methods](https://doi.org/10.1146/annurev-physchem-082720-034254) (Annu. Rev. Phys. Chem., 2022) | Concise overview of NNP methods across four generations | Systematic classification of NNPs from first-generation low-dimensional systems to fourth-generation potentials with nonlocal charge transfer; discusses predefined vs learnable descriptors and message passing networks |
| [Four generations of high-dimensional neural network potentials](https://doi.org/10.1021/acs.chemrev.0c00868) (Chem. Rev., 2021) | Comprehensive review of HDNNP evolution including long-range treatment | Reviews four generations of HDNNPs: from low-dimensional systems to high-dimensional local models, then adding long-range electrostatics via environment-dependent charges, and finally nonlocal charge transfer |
| [Machine learning potentials for extended systems: a perspective](https://doi.org/10.1140/epjb/s10051-021-00156-1) (Eur. Phys. J. B, 2021) | Perspective on ML potentials for materials with long-range interactions | Discusses locality exploitation, long-range electrostatics, and non-local charge transfer in ML potentials for extended systems; covers remaining challenges and three main representation approaches |
| [Long-range electrostatics made easier](https://doi.org/10.1063/5.0316886) (J. Chem. Phys., 2026) | Perspective on LES framework design principles | Distills two key principles: use Coulomb functional with environment-dependent charges, and avoid training on ambiguous DFT partial charges; discusses flexibility and remaining challenges |
| [When short-range models fall short](https://doi.org/10.1063/5.0031215) (J. Chem. Phys., 2021) | Analysis of long-range interaction necessity in ML models | Demonstrates that while local representations suffice for condensed phases, short-range ML models fail for cluster and vapor phases due to missing long-range interactions |
| [General-purpose ML potentials with nonlocal charge transfer](https://doi.org/10.1021/acs.accounts.0c00689) (Acc. Chem. Res., 2021) | Account of fourth-generation NNPs capturing nonlocal phenomena | Overview of machine learning potentials that can describe long-range charge transfer and electronic effects beyond local environments |

---

## 🧠 Reading Map

**If you are new to the field:**

1. Start with PhysNet and SpookyNet to see how molecular MLFFs incorporate charges, dipoles, and dispersion.
2. Read DPLR for periodic long-range electrostatics with Wannier centers.
3. Read EwaldMP, LES, and SOG-Net for current reciprocal-space / latent-variable strategies.
4. Test on at least one charged, polar, interfacial, or noncovalent dataset; short-range validation alone is not enough.

**If you are building a model:**

1. Decide whether the system needs explicit asymptotic physics, learned nonlocal communication, or a hybrid.
2. Check if required labels are available: charges, dipoles, MLWCs, dielectric response, or only energy/force.
3. Verify extensivity, charge neutrality, PBC convention, force consistency, and energy conservation.
4. Compare against a strong short-range baseline plus D3/D4 before claiming long-range gains.

---

## Contributing

We welcome contributions! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and submit a pull request.

Preferred entry format:

```markdown
- Paper Title (Venue, Year) - one sentence on long-range relevance. Include a stable paper link and, if available, a code link.
```

---

## Cite This Repository

If you find this repository useful, please consider citing:

```bibtex
@misc{awesome_mlff_long_range_2026,
  title        = {Awesome Machine Learning Force Fields with Long-Range Interactions},
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
