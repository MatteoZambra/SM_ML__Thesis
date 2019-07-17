# StatisticalMechanics_MachineLearning__MScThesis

## Aim
This repo contains the code intended to support the developing process of my Master Degree Thesis.

## Scope

Motivated by recent publications concerning the development and formalisation of a theoretical framework in which Deep Learning may fit into, this thesis topic and work is finalised to investigate the evolution of the topology of a neural system structure during the process of learning.

In the full swing of the example provided in [2], some synthetic data set are being cratfed, according to some particular morphology (e.g. binary tree structure and independent clusters, created in a _simuated annealing_ fashion), then these are fed to a neural network. A simple feed forward network is accounted for as model zero.

A simple FFNN is inspected as breeding ground for _network motifs_ (in the terms of [4], these are recurrent subgraphs which can be detected more frequrently in the system at hand than in a similar randomized network, this latter generated taking into due account the degree sequence). The interest is to investigate the process of evolution of such motifs and their role (if any), and try to put this phenomenon in relationship with the learning process, that is: How the probabilistic signature of the data fed to the system is encoded in the internal structure of the network itself. A step further that it is in order to be taken is the following: While in the rich pool of previous work on network motifs mining all of the systems are assumed to be _unweighted_ (e.g. [4] and references therein), here one cannot think of neglecting the strengths of connections between neurons. A way to accomplish this may be considering the coherence of a subgraph by evaluating its entropy, intended as a measure of _homogeneity_ of the subgraphs _colors_ (i.e. bins, discrete categories in which the continuous spectrum of edges strengths are divided). Other than that, what sets this work apart from the formerly mentioned literature, is that the system has undergone an evolutionary process driven first and foremost by the optimization algorithm chosen (here SGD is uniquely adopted). A genetics-inspired evolutionary force here may not be a good choice: Parameters must be updated according to optimum rules.

## Contents

`Docs` folder contains an up to date report.

`sources` contains the source codes used for the results. Here there are 

* `DataSets` folder, which contains the scripts to generate the two data sets used. Number of data examples and other details are hard-coded. In addition, serialized files of previously created data sets are present, in order to fetch them in the simulations.
* `FanMod__results` contains the results of the execution of the motifs mining tool [FANMOD](http://theinf1.informatik.uni-jena.de/motifs/), that is postprocessed text files in which only adjacency matrices and motif IDs are retained. This serves to postprocess the motifs informations in the script `main_3_EntropyEval`. 
* `images`, saved plots used in the report.
* `mfinder__Reports`, motifs search outputs generated by the [MFINDER1.2](https://www.weizmann.ac.il/mcb/UriAlon/download/network-motif-software) tool. 
* `Model`, that contains `keras` models in `h5` format. Both untrained and trained (with different data sets) models are present in that th motifs mining analysis is performed in either cases.
* All the scripts used. 
    * The three `main__i_*.py` files, `i = 1,2,3` are the main body of the program. The first concerns model setup and train. The second codes the preprocessing stage, in which the network is prepared in a way amenable to FANMOD. The third serves to the aim to analyse the results of the latter. Might one want to use MFINDER, then this analysis is done by thee `MotifsDetect.py` module, launched in `main_1_.py`.
    * All the others are utility functions or classes separated in different files.

A further improvement could be to gather all these functions in classes, according to their aim, and to create different packages. Furthermore, it could be useful to give the user more ease to change data sets characteristics, avoiding to hard-code these in the aforementioned scripts.



## References

1. [Andrew M. Saxe, James L. McClelland, Surya Ganguli, _Exact solutions to the nonlinear dynamics of learning in deep linear neural networks_, 2014](https://arxiv.org/abs/1312.6120 "arXiv")

2. [Andrew M. Saxe, James L. McClelland, Surya Ganguli, _A mathematical theory of semantic development in deep neural networks_, 2018](https://arxiv.org/abs/1810.10531 "arXiv")

3. [Sebastian Musslick, Andrew M. Saxe, Kayhan Ozcimder, Biswadip Dey, Greg Henselman, Jonathan D. Cohen, _Multitasking Capability Versus Learning Efficiency in Neural Network Architectures_, 2017](https://www.researchgate.net/publication/317019423_Multitasking_Capability_Versus_Learning_Efficiency_in_Neural_Network_Architectures "Research Gate")

4. [Nadav Kashtan and Uri Alon, _Spontaneous evolution of modularity and network motifs_, 2005](https://www.pnas.org/content/102/39/13773 "PNAS")

5. [Pedro Ribeiro and Fernando Silva, _Discovering Colored Network Motifs_Discovering Colored Network Motifs_, 2014](https://link.springer.com/chapter/10.1007/978-3-319-05401-8_11 "Springer")

6. [Sarvenaz Choobdar, Pedro Ribeiro, and Fernando Silva, _Motif Mining in Weighted Networks_, 2012](https://ieeexplore.ieee.org/document/6406443/ "IEEE")

7. [Sebastian Wernicke and Florian Rasche , _FANMOD: a tool for fast network motif detection_, 2006](https://www.ncbi.nlm.nih.gov/pubmed/16455747 "NCBI")
