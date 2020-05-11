# Cogrob Trajectron++ Mods

This repo contains code for 6.832's Grand Challenge (Spring 2020). This team focused on Intent Recognition and [this paper](https://arxiv.org/pdf/2001.03093v2.pdf). This repo contains code relevant to the Trajectron++ portion of the project. This code seperate from the rest of the team's work as it needs to be placed in a specific subdirectory of the Trajectron++ file structure to function properly. The rest of the team's code can be found [here](https://github.com/cog-rob-spring-2020/intent-inferencing-gc).

## Repo Structure

* `./notebooks`: Contains the Jupyter Notebooks for running the code in this repo. The notebooks are numbered in the order you should run them. Read through them for additional documentation/explainations.
* `./modified-trajectron`: Contains the modified versions and `.diff` files for `mgcvae.py` and `trajectron.py`. See section below for additional explanation.
* `./data`: Contains directories for inputs and outputs to the notebooks. Read the notebooks to understand what files should be place/will appear in which directory.

## Setup

1. [Clone Trajectron++ and follow its setup instruction.](https://github.com/StanfordASL/Trajectron-plus-plus) Make sure to setup the conda environment and add the Python kernel to Jupyter.
2. Clone this repo into the Trajectron++ file structure. Specifically, this repo's directory should reside in `Trajectron-plus-plus/experiments/` directory.
3. Modify the **two** Trajectron++ source files `mgcvae.py` and `trajectron.py` as outlined in the below.
4. Run `jupyter-notebook` in this directory and navigate to the `./notebooks` directory.
5. Run through the notebooks, in numbered order, selectively running the cells you desire. Make sure to enable the Python Kernel you made during the Trajectron++ installation process.

## Plotting Modifications to Trajectron++ Source:

The Notebook `02_Evaluate-Data.ipynb` runs Trajectron++ prediction with Trajectron++'s `eval_stg.predict()` function and produces plots of the results.
To expose additional information to the plotting interface, two Trajectron++ source files needed to be modified.
Specifically, the following files were modified:
* `Trajectron-plus-plus/trajectron/model/mgcvae.py`
* `Trajectron-plus-plus/trajectron/model/trajectron.py`

The modified versions of these files can be found in the `./modified-trajectron` directory along with their `.diff` files. Before running this Notebook,
make sure these modifications end up in your working copy of Trajectron++. This can be done by simply replacing the stock Trajectron++ files with the provided
files. Alternatively, you can apply the provided diffs.

## Training Modifications to Trajectron++ Source:

Training a Trajectron++ model is not required for the notebooks to work (i.e. by default the notebooks use the pretrained
`Trajectron-plus-plus/experiments/nuScenes/models/int_ee` model). That being said, if you do want to try training your own model with a CPU, make sure to modify
`Trajectron-plus-plus/trajectron/train.py` [as noted in the Trajectron++ README](https://github.com/StanfordASL/Trajectron-plus-plus#cpu-training)

## Special Thanks

Special thanks to [Boris Ivanovic](https://github.com/BorisIvanovic) for his help getting Trajectron++ running!
