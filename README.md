[arXiv]XXX  |  [Paper] XXX

# DeepStruc
Welcome to DeepStruc that is a Deep Generative Model (DGM) which learns the relation between PDF and atomic structure and thereby solve a structure based on a PDF!

We here apply DeepStruc for the structural analysis of a model system of monometallic nanoparticles (MMNPs) with seven different structure types and demonstrate the method for both simulated and experimental PDFs. DeepStruc can reconstruct simulated data with an average mean absolute error (MAE) of the atom xyz-coordinates on 0.093 ± 0.058 Å after fitting a contraction/extraction factor, an ADP and a scale parameter.
We demonstrate the generative capability of DeepStruc on a dataset of face-centered cubic (fcc), hexagonal closed packed (hcp) and stacking faulted structures, where DeepStruc can recognize the stacking faulted structures as an interpolation between fcc and hcp and construct new structural models based on a PDF. The MAE is in this example 0.030 ± 0.019 Å.

The MMNPs are provided as a graph-based input to the encoder of DeepStruc. We compare the DeepStruc with a similar DGM without the graph-based encoder. DeepStruc is able to reconstruct the structures using a smaller dimension of the latent space thus having a better generative capabillity. We also compared DeepStruc with a brute-force modelling approach and a tree-based classification algorithm. The ML models are significantly faster than the brute-force approach, but DeepStruc can furthermore create a latent space from where synthetic structures can be sampled which the tree-based method cannot!
The baseline models can be found in other repositories: XXX.  YYY.  ZZZ   

![alt text](img/DeepStruc.png "DeepStruc")

## Introduction

The __README.md__ file consist of the following sections:

1. [Getting started](#getting-started)
2. [DeepStruc](#DeepStruc)
    1. [Train model](#train-model)
    2. [Predict](#predict)
    3. [Simulate data](#simulate-data)
3. [Author](#author)
4. [Cite](#cite)
5. [Acknowledgments](#Acknowledgments)
6. [License](#license)

# Getting started


# DeepStruc

## Train model
List of possible arguments or run the '--help' argument for additional information.  
 
| Arg | Description | Example |  
| --- | --- |  --- |  
| `-h` or `--help` | Prints help message. |    
| `-d` or `--data_dir` | Directory containing graph training, validation and test data. __str__| `-d ./data/graphs`  |  
| `-s` or `--save_dir` | Directory where models will be saved. This is also used for loading a learner. __str__ | `-s bst_model`  |   
| `-r` or `--resume_model` | If 'True' the save_dir model is loaded and training is continued. __bool__| `-r True`  |
| `-e` or `--epochs` | Number of maximum epochs. __int__| `-e 100`  |  
| `-b` or `--batch_size` | Number of graphs in each batch. __int__| `-b 20`  |  
| `-l` or `--learning_rate` | Learning rate. __float__| `-l 1e-4`  |  
| `-B` or `--Beta` | Initial beta value for scaling KLD. __float__| `-B 0.1`  |  
| `-i` or `--beta_increase` | "Increments of beta when the threshold is met. __float__| `-i 0.1`  |  
| `-x` or `--beta_max` | Highst value beta can increase to. __float__| `-x 5`  |  
| `-t` or `--reconstruction_th` | Reconstruction threshold required before beta is increased. __float__| `-t 0.001`  |  
| `-n` or `--num_files` | Total number of files loaded. Files will be split 60/20/20. If 'None' then all files are loaded. __int__| `-n 500`  |  
| `-c` or `--compute` | Train model on CPU or GPU. Choices: 'cpu', 'gpu16', 'gpu32' and 'gpu64'. __str__| `-c gpu32`  |  
| `-L` or `--latent_dim` | Number of latent space dimensions. __int__| `-L 3`  |  

## Predict

## Simulate data
See the __data__ folder. 

# Authors
* __Andy S. Anker__, Ph.D. student in Nanoscience at the University of Copenhagen   
* __Emil T. S. Kjær__, Ph.D. student in Nanoscience at the University of Copenhagen   
* Supervisor __Kirsten M. Ø. Jensen__, associate professor at the University of Copenhagen.  
 
Should there be any question, desired improvement or bugs please contact us on GitHub or 
through email: __andy@chem.ku.dk__ or __etsk@chem.ku.dk__.

# Cite
If you use our code or our results, please consider citing our paper. Thanks in advance!
```
@article{kjær2022DeepStruc,
title={DeepStruc: Towards structure solution from pair distribution function data using deep generative models},
author={Emil T. S. Kjær, Andy S. Anker, Marcus N. Weng1, Simon J. L. Billinge, Raghavendra Selvan, Kirsten M. Ø. Jensen},
year={2022}}
```

# Acknowledgments
Our code is developed based on the the following publication:
```
@article{anker2020characterising,
title={Characterising the atomic structure of mono-metallic nanoparticles from x-ray scattering data using conditional generative models},
author={Anker, Andy Sode and Kjær, Emil TS and Dam, Erik B and Billinge, Simon JL and Jensen, Kirsten MØ and Selvan, Raghavendra},
year={2020}}
```

# License
This project is licensed under the XXX License - see the [LICENSE.md](LICENSE.md) file for details.
