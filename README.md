# Predicting MoA (Mechanisms of Action) Annotations
## Goals
To predict MoA annotations based on drugs' biological response.
## Background
From [**Kaggle**](https://www.kaggle.com/c/lish-moa):<br>
"Today, with the advent of more powerful technologies, drug discovery has changed from the serendipitous approaches of the past to a more targeted model based on an understanding of the underlying biological mechanism of a disease. In this new framework, scientists seek to identify a protein target associated with a disease and develop a molecule that can modulate that protein target. As a shorthand to describe the biological activity of a given molecule, scientists assign a label referred to as mechanism-of-action or MoA for short.<br>
One approach is to treat a sample of human cells with the drug and then analyze the cellular responses with algorithms that search for similarity to known patterns in large genomic databases, such as libraries of gene expression or cell viability patterns of drugs with known MoAs."

## Acknowledgements

## Data Dictionary
**sig_id:** A Connectivity Map unique identification number assigned to each signature generated from L1000 assay. A signature is the entire vector of differential expression values, one per gene. The signature provides a representation of the biological response. Besides gene expression data, <br>
**cp_type:** indicates how the samples are treated: either with small-molecule compounds(trt_cp) or with a control perturbation (ctrl_vehicle). Control pertubations have no MoAs.<br> 
**cp_time:** indicates treatment time: 24, 48, and 72 hours.<br> 
**cp_does:** indicates treatment does: high or low.<br>
**g-#:** signify gene expression data. There are 772 gene features for each sig_id. Every expression data describes the degree to which a gene's expression is increased or decreased in response to a chemical perturbagen.<br>
**c-#:** signify cell viability data. There are 100 cell lines for each sig_id, which are assessed collectively by PRISM (Profiling Relative Inhibition Simultaneously in Mixture).<br> 

## Key Concepts Explained
**L1000 assay:** a high-throughput gene expression assay that measures the mRNA transcript abundance of 978 "landmark" genes from human cells. 

## Initial Thoughts & Hypotheses
### Thoughts
- The cellualr responses are measured by two ways: gene expression and cell viability.
- Gene expression and cell viability are related in someway. 
- The cell viability of contorl samples is sigfinicantly different from the that of treated samples.
- There is no significant difference in cell viability and gene expression among the 100 cell lines in the control samples.
    - Because the controls have little impact on the cells, so the dose and time don’t have a significant impact on the gene expression and cell viability data for controls. 

### Hypotheses
#### Gene expressions data in controls are the same over time
H_0: The average gene expressions in control with dose 2 are the same at 24 vs. 48 hours.<br>
H_a: The average gene expressions in control with dose 2 are significantly different at 24 vs. 48 hours.<br>

H_0: The average gene expressions in control with dose 2 are the same at 48 vs. 72 hours.<br>
H_a: The average gene expressions in control with dose 2 are significantly different at 48 vs. 72 hours.<br>

#### Gene expressions in one observation are normally distributed. 
H_0: The gene expression in one observation are normally distributed.
H_a: The gene expression in one observation are not normally distributed. 

## Reference
- [**Mechanisms of Action (MoA) Prediction Description**](https://www.kaggle.com/c/lish-moa/overview/description)
- [**Connectopedia**](https://clue.io/connectopedia/glossary)
- [**Corsello et al. “Discovering the anticancer potential of non-oncology drugs by systematic viability profiling,” Nature Cancer, 2020**](https://doi.org/10.1038/s43018-019-0018-6)
- [**Subramanian et al. “A Next Generation Connectivity Map: L1000 Platform and the First 1,000,000 Profiles,” Cell, 2017**](https://doi.org/10.1016/j.cell.2017.10.049)