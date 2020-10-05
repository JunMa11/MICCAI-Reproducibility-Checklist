>A template README.md for code accompanying a machine learning-based MICCAI paper, which is built on [paperswithcode/releasing-research-code](https://github.com/paperswithcode/releasing-research-code).
>
>Dataset, preprocessing, posting processing sections are added because these parts are very important to reproduce the results in medical image analysis community.

# My Paper Title

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
