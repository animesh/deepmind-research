## setup

python3 -m venv alphafold_venv
git clone https://github.com/animesh/deepmind-research.git
cd deepmind-research
source alphafold_venv/bin/activate
pip install wheel
pip install -r alphafold_casp13/requirements.txt
#./alphafold_casp13/run_eval.sh
#https://chrome.google.com/webstore/detail/curlwget/jmocjfidanebdlinpbcdkcmgdifblncg?hl=en
wget --header="Host: storage.googleapis.com" --header="User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.87 Safari/537.36" --header="Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9" --header="Accept-Language: en-IN,en;q=0.9,hi-IN;q=0.8,hi;q=0.7,nb-NO;q=0.6,nb;q=0.5,de-DE;q=0.4,de;q=0.3,en-GB;q=0.2,en-US;q=0.1" "https://storage.googleapis.com/alphafold_casp13_data/casp13_data.zip" -O "casp13_data.zip" -c
unzip casp13_data.zip
wget --header="Host: storage.googleapis.com" --header="User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.87 Safari/537.36" --header="Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9" --header="Accept-Language: en-IN,en;q=0.9,hi-IN;q=0.8,hi;q=0.7,nb-NO;q=0.6,nb;q=0.5,de-DE;q=0.4,de;q=0.3,en-GB;q=0.2,en-US;q=0.1" "https://storage.googleapis.com/alphafold_casp13_data/alphafold_casp13_weights.zip" -O "alphafold_casp13_weights.zip" -c
unzip alphafold_casp13_weights.zip
python3 -m alphafold_casp13.contacts --config_path=873731/0/config.json --checkpoint_path=873731/0/tf_graph_data/tf_graph_data.ckpt --output_path=chkout --eval_sstable=T1019s2/T1019s2.tfrec --stats_file=873731/stats_train_s35.json

# DeepMind Research

This repository contains implementations and illustrative code to accompany
DeepMind publications. Along with publishing papers to accompany research
conducted at DeepMind, we release open-source
[environments](https://deepmind.com/research/open-source/open-source-environments/),
[data sets](https://deepmind.com/research/open-source/open-source-datasets/),
and [code](https://deepmind.com/research/open-source/open-source-code/) to
enable the broader research community to engage with our work and build upon it,
with the ultimate goal of accelerating scientific progress to benefit society.
For example, you can build on our implementations of the
[Deep Q-Network](https://github.com/deepmind/dqn) or
[Differential Neural Computer](https://github.com/deepmind/dnc), or experiment
in the same environments we use for our research, such as
[DeepMind Lab](https://github.com/deepmind/lab) or
[StarCraft II](https://github.com/deepmind/pysc2).

If you enjoy building tools, environments, software libraries, and other
infrastructure of the kind listed below, you can view open positions to work in
related areas on our [careers page](https://deepmind.com/careers/).

For a full list of our publications, please see
https://deepmind.com/research/publications/

## Projects

*   [AlphaFold CASP13](alphafold_casp13), Nature 2020
*   [Unrestricted Adversarial Challenge](unrestricted_advx)
*   [Hierarchical Probabilistic U-Net (HPU-Net)](hierarchical_probabilistic_unet)
*   [Training Language GANs from Scratch](scratchgan), NeurIPS 2019
*   [Temporal Value Transport](tvt), Nature Communications 2019
*   [Continual Unsupervised Representation Learning (CURL)](curl), NeurIPS 2019
*   [Unsupervised Learning of Object Keypoints (Transporter)](transporter), NeurIPS 2019
*   [BigBiGAN](bigbigan), NeurIPS 2019
*   [Deep Compressed Sensing](cs_gan), ICML 2019
*   [Side Effects Penalties](side_effects_penalties)
*   [PrediNet Architecture and Relations Game Datasets](PrediNet)
*   [Unsupervised Adversarial Training](unsupervised_adversarial_training), NeurIPS 2019
*   [Graph Matching Networks for Learning the Similarity of Graph Structured
    Objects](graph_matching_networks), ICML 2019
*   [REGAL: Transfer Learning for Fast Optimization of Computation Graphs](regal)

## Disclaimer

*This is not an official Google product.*
