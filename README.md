# Feature-Center-Constraint

## Overview

This repository provides the source code from the following paper.

**Applying feature-similarity-metrics for long-tailed problem of phytoplankton microscopic images classification**

## Usage

This repository primarily provides the configuration files, experimental results, and some image resources used in the paper. 

The main source code for the project is included in other repository [TorchSweetie](https://github.com/SikaAntler/TorchSweetie). Therefore, please following the README file to install and active the environment first.

## Configuration

Following by the module `TorchSweetie`, we used configuration files to manage the experiments. 

All configuration files were stored in the directory `./configs/`.

As you can see, to ensure a fair comparison of various methods, we firstly wrote a basic configuration, including backbone network, dataset, optimizer, epochs, etc.

Based on this, we created a new configuration for each method. The details are shown in the table below:

|          Category          |                 Method                  | Micro-Avg | Macro-Avg |
| :------------------------: | :-------------------------------------: | :-------: | :-------: |
|          General           | [Cross-Entropy Loss](./configs/base.py) |   0.879   |   0.785   |
|        Re-sampling         |       [Class-Balanced Sampling]()       |     /     |     /     |
|                            |        [Square-Root Sampling]()         |   0.898   |   0.820   |
|                            |         [Decoupling Training]()         |   0.748   |   0.635   |
|        Re-weighting        |            [Re-weighting]()             |   0.851   |   0.763   |
|                            |    [$\tau$-normalized Classifier]()     |     /     |     /     |
|                            |          [Effective-Number]()           |   0.896   |   0.819   |
|                            |        [Balanced-Softmax Loss]()        |   0.916   |   0.793   |
|                            |         [Logit-Adjusted Loss]()         |   0.893   |   0.804   |
| Feature-Similarity-Metrics |      [Feature-Center-Constraint]()      | **0.929** | **0.878** |

