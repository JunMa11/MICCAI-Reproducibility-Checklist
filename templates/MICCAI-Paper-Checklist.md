# MICCAI-Paper-Checklist
> The checklist builds on the [machine learning reproducibility checklist](https://www.cs.mcgill.ca/~jpineau/ReproducibilityChecklist.pdf), but is specific to MICCAI papers.
> We also got lots of insights from
>
> - Mongan, John, Linda Moy, and Charles E. Kahn Jr. "Checklist for Artificial Intelligence in Medical Imaging (CLAIM): A guide for authors and reviewers." Radiology: Artificial Intelligence (2020): e200029.
> - Norgeot, Beau, Giorgio Quer, Brett K. Beaulieu-Jones, Ali Torkamani, Raquel Dias, Milena Gianfrancesco, Rima Arnaout et al. "Minimum information about clinical artificial intelligence modeling: the MI-CLAIM checklist." Nature Medicine 26, no. 9 (2020): 1320-1324
> - Reproducibility Criteria in [ELNMP 2020](https://2020.emnlp.org/call-for-papers)
>

### Methods

- A clear description of the mathematical setting, algorithm, and/or model.
- Network architecture details
    - layer details in each block/module
    - the number of parameters
- Explanation of evaluation metrics (with links to code)

### Experiments

- Dataset
    - for public dataset, providing data sources, e.g, references and URL links
    - for private dataset, providing the data acquisition source and characteristics (e.g., device, contrast agent...), the eligibility description, the ground truth standard (e.g., qualifications and preparation of annotators), annotation tools, analysis of inter-rater variability
    - details of train / validation / test splits
- Preprocessing steps
    - cropping strategy
    - resampling method for anisotropic data
    - intensity normalization method
    - registration method for multi-sequence/modality data
- Training protocols
    - computing infrastructure (e.g., GPU name, number, memory)
    - patch size and patch sampling strategy
    - batch size
    - optimizer, learning rate and its decay schedule 
    - loss function 
    - data augmentation methods
    - stopping criteria, and optimal model selection criteria
    - training time
- Testing steps
    - if using patch-based strategy, describing the patch aggregation method
    - inference time
- Postprocessing steps
- Ablation study

### Results
- Quantitative analysis of cross validation results and/or testing set results
    - average and standard deviation of evaluation metrics
    - statistical analysis (e.g., statistical methods, significant levels...)

- Qualitative analysis
    - box/violin plot, ROC curves
    - visualized examples of both successful and **failed** cases
