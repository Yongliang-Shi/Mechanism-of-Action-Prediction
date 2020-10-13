# Predicting MoA (Mechanisms of Action) Annotations
## Goals
To predict MoA annotations based on drugs' biological response.
## Data Dictionary
**sig_id:** A Connectivity Map unique identification number assigned to each signature generated from L1000 assay. A signature is the entire vector of differential expression values, one per gene. The signature provides a representation of the biological response. 
**cp_type:** indicates how the samples are treated: either with small-molecule compounds(trt_cp) or with a control perturbation (ctrl_vehicle). Control pertubations have no MoAs.
**cp_time:** indicates treatment time: 24, 48, and 72 hours.
**cp_does:** indicates treatment does: high or low. 
**g-#:** signify gene expression data. There are 772 gene features for each sig_id. Every expression data describes the degree to which a gene's expression is increased or decreased in response to a chemical perturbagen. 
**c-#:** signify cell viability data. There are 100 cell lines for each sig_id, which are assessed collectively by PRISM (Profiling Relative Inhibition Simultaneously in Mixture). 