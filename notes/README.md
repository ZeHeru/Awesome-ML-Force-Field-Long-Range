# Notes and Mind Maps

This folder contains mind map notes (`.mmd` files) for papers related to long-range interactions in machine learning force fields.

## Available Notes (33 note files)

### Review Papers and Perspectives
- [Long-Range_Electrostatics_Made_Easier.mmd](Long-Range_Electrostatics_Made_Easier.mmd) - Perspective on LES framework design principles for long-range electrostatics
- [ShortRange_ML_Limits_Yue_JCP_2021.mmd](ShortRange_ML_Limits_Yue_JCP_2021.mmd) - Analysis of when short-range ML models fail due to missing long-range interactions
- [FourGen_NNP_Review_Behler_ChemRev_2021.mmd](FourGen_NNP_Review_Behler_ChemRev_2021.mmd) - Comprehensive review of four generations of HDNNPs including long-range treatment
- [FourGen_NNP_AccChemRes_Ko_2021.mmd](FourGen_NNP_AccChemRes_Ko_2021.mmd) - Account of fourth-generation NNPs capturing nonlocal charge transfer
- [ExtendedSystems_MLP_Review_Behler_Csanyi_EPJB_2021.mmd](ExtendedSystems_MLP_Review_Behler_Csanyi_EPJB_2021.mmd) - Perspective on ML potentials for extended systems with long-range interactions
- [machine-learning-interatomic-potentials-and-long-range-physics.mmd](machine-learning-interatomic-potentials-and-long-range-physics.mmd) - Comprehensive review on long-range physics in MLIPs

### Charge and Electrostatics Models
- [PhysNet_Unke_Meuwly_JCTC_2019.mmd](PhysNet_Unke_Meuwly_JCTC_2019.mmd) - PhysNet with charges and dipoles
- [SpookyNet_Unke_NatComm_2021.mmd](SpookyNet_Unke_NatComm_2021.mmd) - Electronic degrees of freedom and nonlocal effects
- [FourGNNP_Ko_Behler_NatComm_2021.mmd](FourGNNP_Ko_Behler_NatComm_2021.mmd) - 4G-HDNNP with charge transfer
- [AIMNet_NSE_Zubatyuk_NatComm_2021.mmd](AIMNet_NSE_Zubatyuk_NatComm_2021.mmd) - AIMNet neural sum of energies
- [AIMNet_Zubatyuk_SciAdv_2019_SI.mmd](AIMNet_Zubatyuk_SciAdv_2019_SI.mmd) - Original AIMNet
- [HIPNN_Charge_Sifain_JPCL_2018.mmd](HIPNN_Charge_Sifain_JPCL_2018.mmd) - Hierarchical interacting particle NN with charges
- [SCFNN_Gao_Remsing_NatComm_2022.mmd](SCFNN_Gao_Remsing_NatComm_2022.mmd) - Self-consistent field neural network
- [BpopNN_Xie_JCTC_2020.mmd](BpopNN_Xie_JCTC_2020.mmd) - Bond-order potential neural network
- [CENT_Ghasemi_PRB_2015.mmd](CENT_Ghasemi_PRB_2015.mmd) - Charge equilibration neural network
- [BAMBOO.mmd](BAMBOO.mmd) - Liquid electrolyte MLFF framework

### Ewald and Long-Range Methods
- [LES_Universal_Augmentation_Long_Range.mmd](LES_Universal_Augmentation_Long_Range.mmd) - Latent Ewald summation augmentation
- [Latent_Ewald_Summation.mmd](Latent_Ewald_Summation.mmd) - Latent Ewald summation for long-range interactions
- [Deep_Potential_Long_Range.mmd](Deep_Potential_Long_Range.mmd) - DPLR with Wannier centers
- [SO3LR_Molecular_Simulations_Pretrained_NN_Pairwise_FF.mmd](SO3LR_Molecular_Simulations_Pretrained_NN_Pairwise_FF.mmd) - SO3LR for long-range systems
- [SOG-Net.mmd](SOG-Net.mmd) - Sum-of-Gaussians neural network for long-range systems
- [CACE-SOG_coupling.mmd](CACE-SOG_coupling.mmd) - Coupling CACE and SOG-Net for long-range potentials
- [Euclidean_Fast_Attention.mmd](Euclidean_Fast_Attention.mmd) - Linear-scaling attention with Euclidean rotary positional encoding for global interactions
- [FENNIX.mmd](FENNIX.mmd) - Force field enhanced neural network for long-range interactions
- [Foundation_MLIP_with_Polarizable_Long-Range.mmd](Foundation_MLIP_with_Polarizable_Long-Range.mmd) - Foundation model with polarizable long-range interactions
- [DeepWannier_Dielectric_Zhang_PRB_2020.mmd](DeepWannier_Dielectric_Zhang_PRB_2020.mmd) - Wannier centers for dielectric response
- [LongRange_ChargedDimers_Grisafi_Ceriotti_JCP_2019.mmd](LongRange_ChargedDimers_Grisafi_Ceriotti_JCP_2019.mmd) - Long-range interactions in charged dimers

### Polarization, Multipoles, and Electric Response
- [Machine_learning_interatomic_potential_can_infer_electrical_response.mmd](Machine_learning_interatomic_potential_can_infer_electrical_response.mmd) - LES-based electrical response, polarization, and Born effective charges
- [ANI_AMOEBA_Inizan_ChemSci_2023.mmd](ANI_AMOEBA_Inizan_ChemSci_2023.mmd) - ANI with AMOEBA polarizable force field
- [AA_Multipole_Kriging_Fletcher_Popelier_JCTC_2016.mmd](AA_Multipole_Kriging_Fletcher_Popelier_JCTC_2016.mmd) - Atomic multipole kriging

### Dispersion and van der Waals
- [MBD_Benzene_Tkatchenko_PRL_2012.mmd](MBD_Benzene_Tkatchenko_PRL_2012.mmd) - Many-body dispersion
- [vdW_Water_Morawietz_PNAS_2016.mmd](vdW_Water_Morawietz_PNAS_2016.mmd) - van der Waals interactions in water

### Neural Network Architectures
- [SchNetPack.mmd](SchNetPack.mmd) - SchNetPack atomistic deep learning toolbox
- [SchNetPack_2.mmd](SchNetPack_2.mmd) - SchNetPack 2.0 atomistic machine learning toolbox

---

## Papers Without MMD Notes

The following papers mentioned in the main README do not yet have mind map notes:

### Core Papers
- CELLI (Charge Equilibration, 2025)
- EwaldMP (2023)
- Variational charge equilibration (2024) - **Removed**: content was unrelated to long-range MLFFs
- Reciprocal Space Neural Network

### Software
- AIMNetCentral
- DMFF

---

## Removed Files

The following files were removed as they were not primarily focused on long-range interactions in MLFFs:

- **Variational_charge_equilibration.mmd** - Content was about electron microscopy image segmentation, not long-range MLFFs
- **NNP_WaterClusters_Morawietz_Behler_JPCA_2013.mmd** - Application paper, not focused on long-range methods
- **ZnO_NNP_Artrith_Morawietz_Behler_PRB_2011.mmd** - Application paper for ZnO
- **Phosphorus_GAP_Deringer_NatComm_2020.mmd** - General-purpose GAP, not long-range focused
- **C60_PhaseDiagram_Muhli_PRB_2021.mmd** - Application paper with vdW, but not long-range focused
- **Li3N_ESNAP_Deng_Ong_npjCM_2019.mmd** - Application paper for Li3N
- **NNRF_CHNO_RDX_Yoo_npjCM_2021.mmd** - Reactive force field application
- **Alanine_Kriging_Mills_Popelier_TCA_2012.mmd** - Specific application to alanine
- **SchNet_Schutt_JCP_2018.mmd** - General architecture, not long-range focused
- **DTNN_Schutt_NatComm_2017.mmd** - General architecture, not long-range focused

---

**Note**: If you have created mind maps for any of the papers listed in "Papers Without MMD Notes", please add them to this folder and update this README.
