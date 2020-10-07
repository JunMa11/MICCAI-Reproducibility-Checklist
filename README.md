# MICCAI-Reproducibility-Checklist
Submission for [MICCAI HACKATHON]( https://miccai-hackathon.com/#participate)

**REPRODUCIBILITY 1: WHAT DOES IT NEED FOR A MICCAI PAPER TO BE REPRODUCIBLE?**

1. Create a machine learning reproducibility checklist specific to MICCAI papers.
2. Propose a machine learning code completeness checklist specific to MICCAI papers.
3. How to ensure reproducibility when the data cannot be shared?

# 1. Reproducibility checklist for machine learning-based MICCAI papers

The checklist builds on the [machine learning reproducibility checklist](https://www.cs.mcgill.ca/~jpineau/ReproducibilityChecklist.pdf), but is specific to MICCAI papers.
We also got lots of insights from

- Mongan, J., Moy, L., & Kahn Jr, C. E. Checklist for Artificial Intelligence in Medical Imaging (CLAIM): A guide for authors and reviewers. Radiology: Artificial Intelligence, 2:2 (2020).
- Norgeot, B., Quer, G., Beaulieu-Jones, B.K. et al. Minimum information about clinical artificial intelligence modeling: the MI-CLAIM checklist. Nature Medicine 26, 1320–1324 (2020).
- Reproducibility Criteria in [ELNMP 2020](https://2020.emnlp.org/call-for-papers)

## Methods

- A clear description of the mathematical setting, algorithm, and/or model.
- Network architecture details
  - layer details in each block/module
  - the number of parameters
- Explanation of evaluation metrics (with links to code)

## Experiments

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

## Results

- Quantitative analysis of cross validation results and/or testing set results
  - average and standard deviation of evaluation metrics
  - statistical analysis (e.g., statistical methods, significant levels...)

- Qualitative analysis
  - box/violin plot, ROC curves
  - visualized examples of both successful and **failed** cases




# 2. Code checklist for machine learning-based MICCAI papers
>A template README.md for code accompanying a Machine Learning-based MICCAI paper, which is built on [paperswithcode/releasing-research-code](https://github.com/paperswithcode/releasing-research-code).
>
>Dataset, preprocessing, posting processing sections are added because these parts are very important to reproduce the results in medical image analysis community.

This repository is the official implementation of [My Paper Title](TBA). 

>Optional: include a graphic explaining your approach/main result, bibtex entry, link to demos, blog posts and tutorials

## Environments and Requirements

- Windows/Ubuntu version
- CPU, RAM, GPU information
- CUDA version
- python version

To install requirements:

```setup
pip install -r requirements.txt
```

>Describe how to set up the environment, e.g. pip/conda/docker commands, download datasets, etc...



## Dataset

- A link to download the data (if publicly available)
- A description about how to prepare the data (e.g., folder structures)

## Preprocessing

A brief description of preprocessing method

- cropping
- intensity normalization
- resampling

Running the data preprocessing code:

```python
python preprocessing.py --input_path <path_to_input_data> --output_path <path_to_output_data>
```

## Training

To train the model(s) in the paper, run this command:

```train
python train.py --input-data <path_to_data> --alpha 10 --beta 20
```

>Describe how to train the models, with example commands, including the full training procedure and appropriate hyper-parameters.



## Trained Models

You can download trained models here:

- [My awesome model](https://drive.google.com/mymodel.pth) trained on the above dataset with the above code. 

>Give a link to where/how the trained models can be downloaded.



## Inference

To infer the testing cases, run this command:

```python
python inference.py --input-data <path_to_data> --model_path <path_to_trained_model> --output_path <path_to_output_data>
```

> Describe how to infer on testing cases with the trained models.



## Evaluation

To compute the evaluation metrics, run:

```eval
python eval.py --seg_data <path_to_inference_results> --gt_data <path_to_ground_truth>
```

>Describe how to evaluate the inference results and obtain the reported results in the paper.



## Results

Our method achieves the following performance on [Brain Tumor Segmentation (BraTS) Challenge](https://www.med.upenn.edu/cbica/brats2020/)

| Model name       |  DICE  | 95% Hausdorff Distance |
| ---------------- | :----: | :--------------------: |
| My awesome model | 90.68% |         32.71          |

>Include a table of results from your paper, and link back to the leaderboard for clarity and context. If your main result is a figure, include that figure and link to the command or notebook to reproduce it. 


## Contributing

>Pick a licence and describe how to contribute to your code repository. 

## Acknowledgement

> We thank the contributors of public datasets. 


# 3. How to ensure reproducibility when the data cannot be shared?

- Try to find a related public dataset to evaluate your method, e.g., [The Cancer Imaging Archive](https://www.cancerimagingarchive.net/), [grand-challenge](https://grand-challenge.org/challenges/). If none of the public datasets can be used to evaluate your method, please explicitly claim it, which is very helpful for communities to create task-driven public datasets.
- Create a docker container to pack and share the proposed method. Many MICCAI challenges have used the docker as the submission, e.g., [ADAM](http://adam.isi.uu.nl/methods/submit/), [M&Ms](https://www.ub.edu/mnms/)

