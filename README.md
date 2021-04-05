# Implementation of Explainable AI Classification model by Fan et al. 

Explainable AI classifiers are focused towards determining what features of a dataset are responsible for each respective prediction. In sensitive fields such as medicine, risk assessment, and financial analysis, determining what particular feature contributed to a prediction is almost as important as the prediction itself. For some fields (emphasis on medical), this interpretation of feature importance may also deem to be necessary, because such AI systems are meant to augment professional decision making rather than replace them.  

The [paper](https://arxiv.org/abs/2005.02074) [1] by Fan et al. describes an algorithm for a explainable AI classifier based on probability logic inference. This repository is an implementation of that code in python. Not only does Fan et al. propose algorithms to construct a concrete knowledge base (at the crux of the probabilistic model), they also define a way to simplify the linear system that results when the knowledge base is queried. This method is tolerant to inconsistent knowledge bases, and also provides means to limit the scope of the solver for faster but still accurate predictions and explanations.  

This repository contains two notebooks, one dealing with [probabilistic models](https://github.com/saadejazz/explain_prob/blob/master/heart_fan_prob.ipynb) (Naive Bayes and the explainable model by Fan et al.) and the other dealing with [miscellaneous models](https://github.com/saadejazz/explain_prob/blob/master/heart_misc.ipynb) (Random Forrests and Neural Networks). 

The repository also include critical reviews of two papers: "Explainable AI for Classification using Probabilistic Logic Inference" by Fan et al. and "Causability and explainability of artificial intelligence in medicine" by Holzinger et al., in the folder [critical reviews/](https://github.com/saadejazz/explain_prob/tree/master/critical%20reviews). Furthermore, this repository also includes a paper based on the results of code in this repository. This paper can be found [here](https://github.com/saadejazz/explain_prob/blob/master/paper/Implementation%20of%20an%20Explainable%20AI%20classifier%20for%20Heart%20Disease%20Detection.pdf).

## Getting Started  

To run this code, you would first need to clone this repository using:  
```bash
git clone https://www.github.com/saadejazz/explain_prob
```

Following this you would need to fulfill the following requirements through pip or conda:  
1. [scikit-learn](https://pypi.org/project/scikit-learn/) [2]
2. [pandas](https://pypi.org/project/pandas/)
3. [numpy](https://pypi.org/project/numpy/)
4. [matplotlib](https://pypi.org/project/matplotlib/)
5. [gurobipy](https://www.gurobi.com/documentation/9.1/quickstart_mac/cs_using_pip_to_install_gr.html) 
6. [notebook](https://pypi.org/project/notebook/)

This can be done through pip using the following commands:  
```bash
python -m pip install -i https://pypi.gurobi.com gurobipy
python -m pip install numpy pandas matplotlib scikit-learn
```

Additionally, if you plan on running the miscellaneous models too, you would need to install tensorflow using the guidlines presented [here](https://www.tensorflow.org/install), and [keras](https://pypi.org/project/Keras/).  

Moreover, the probabilistic model by Fan et al. utilizes a linear solver. [Gurobi](https://www.gurobi.com/) has been used in this implementation. You will have to get a trial lisence from [here](https://www.gurobi.com/academia/academic-program-and-licenses/). Please note that without the lisence, the script may not work; so it is imperative, that **the user correctly installs the optimizer and the lisence in the correct path according to their OS** (steps provided in the link). 

There are two notebooks in this repository:  
1. [heart_fan_prob.ipynb](https://github.com/saadejazz/explain_prob/blob/master/heart_fan_prob.ipynb) for probabilistic models
2. [heart_misc.ipynb](https://github.com/saadejazz/explain_prob/blob/master/heart_misc.ipynb) for miscellaneous models

Navigate to the folder where these files are stored, and run notebook to access them. Make sure you have activated your virtual environment beforehand, and have also installed your Gurobi lisence in the appropriate directory:  
```bash
cd explain_prob/
jupyter notebook
```
This will open the notebook homepage, from where you can easily access both scripts. The probabilistic models have a detailed description and directions inside the notebook. The miscellaneous models are intuitive enough to not require directions to run (since they are built upon high level libraries: scikit-learn, keras).  

## References  
1. Fan, Xiuyi, Siyuan Liu, and Thomas C. Henderson. "Explainable AI for Classification using Probabilistic Logic Inference." arXiv preprint arXiv:2005.02074 (2020).
2. Holzinger, Andreas, Georg Langs, Helmut Denk, Kurt Zatloukal, and Heimo Müller. "Causability and explainability of artificial intelligence in medicine." Wiley Interdisciplinary Reviews: Data Mining and Knowledge Discovery 9, no. 4 (2019): e1312.
3. Scikit-learn: Machine Learning in Python, Pedregosa et al., JMLR 12, pp. 2825-2830, 2011.
