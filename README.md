# Predicting MoA (Mechanisms of Action) Annotations
## Goals
To predict MoA annotations based on drugs' biological response.
## Background
From [**Kaggle**](https://www.kaggle.com/c/lish-moa):<br>
"Today, with the advent of more powerful technologies, drug discovery has changed from the serendipitous approaches of the past to a more targeted model based on an understanding of the underlying biological mechanism of a disease. In this new framework, scientists seek to identify a protein target associated with a disease and develop a molecule that can modulate that protein target. As a shorthand to describe the biological activity of a given molecule, scientists assign a label referred to as mechanism-of-action or MoA for short.<br>
One approach is to treat a sample of human cells with the drug and then analyze the cellular responses with algorithms that search for similarity to known patterns in large genomic databases, such as libraries of gene expression or cell viability patterns of drugs with known MoAs."

## Acknowledgements

## Data Dictionary
**sig_id:** A Connectivity Map unique identification number assigned to each signature generated from L1000 assay. A signature is the entire vector of differential expression values, one per gene. The signature provides a representation of the biological response.<br>
**cp_type:** indicates how the samples are treated: either with small-molecule compounds(trt_cp) or with a control perturbation (ctrl_vehicle). Control pertubations have no MoAs.<br> 
**cp_time:** indicates treatment time: 24, 48, and 72 hours.<br> 
**cp_does:** indicates treatment does: high or low.<br>
**g-#:** signify gene expression data. There are 772 gene features for each sig_id. Every expression data describes the degree to which a gene's expression is increased or decreased in response to a chemical perturbagen.<br>
**c-#:** signify cell viability data. There are 100 cell lines for each sig_id, which are assessed collectively by PRISM (Profiling Relative Inhibition Simultaneously in Mixture).<br> 

## Initial Thoughts & Hypotheses
- The cellualr responses are measured by two ways: gene expression and cell viability.
- Gene expression and cell viability are related in someway. 
- The cell viability of contorl samples is sigfinicantly different from the that of treated samples.
- There is no significant difference in cell viability and gene expression among the 100 cell lines in the control samples.
    - Because the controls have little impact on the cells, so the dose and time don’t have a significant impact on the gene expression and cell viability data for controls. 
