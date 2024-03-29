# Autors

José Ribeiro - site: https://sites.google.com/view/jose-sousa-ribeiro

Níkolas Carneiro - site: https://br.linkedin.com/in/nikolas-carneiro-62b6568

Ronnie Alves (Leader) - site: https://sites.google.com/site/alvesrco

# ConeXi

This is a library developed during the article **"Black Box Model Explanations and the Human Interpretability Expectations - An Analysis in the Context of Homicide Prediction"**, by José Ribeiro, Nikolas Carneiro and Ronnie alves.

The main function of this library is to perform the combination of ranks, with or without loss of elements, in a final rank that represents the ideal combination of all ranks passed as input.

In a practical way, this library can be used to combine the output of several Explainable Artificial Intelligence - XAI measures aimed at the global explanation of black box models. Combining them or not, with output from human experts.

The possibility of using this library is varied, not limited to the XAI area.

# Intallation

```Nushell
pip install ConeXi
```

# Import

```Python
from combineranks import ConeXi as combine
```

# Simple execution

In this example, 3 different ranks (rank1, rank2 and rank3) containing 5 elements (attributes) each will be combined into a single final rank.

This is the initial dataframe needed for execution:

```
rank1 rank2 rank3
A    A    A
B    C    B
C    B    C
D    D    D
```

This is the python code:

```Python
#Simple example of utilization of ConeXi
d = {'att_original_names': ['A', 'B','C','D'],
    'weights': [ 1 , 1 , 1 , 1],
    'rank1': ['A', 'B','C','D'],
    'rank2': ['A','C','B','D'],
    'rank3':['A','B','C','D']}
df = pd.DataFrame(data=d)
    
c = combine.ConeXi(4)
    
rank_final, data = c.ExecuteConeXi(df)
    
print(rank_final)
```
This is the output of execution:

```Python
att_original_names    S    
A                   12.0
B                    8.0
C                    7.0
D                    3.0
```

# Cite this work

You can cite the package using the following bibtex entry:
```TeX
@misc{https://doi.org/10.48550/arxiv.2210.10849,
  doi = {10.48550/ARXIV.2210.10849},
  url = {https://arxiv.org/abs/2210.10849},
  author = {Ribeiro, José and Carneiro, Níkolas and Alves, Ronnie},
  keywords = {Machine Learning (cs.LG), Artificial Intelligence (cs.AI), FOS: Computer and information sciences, FOS: Computer and information sciences, I.2.6},
  title = {Black Box Model Explanations and the Human Interpretability Expectations -- An Analysis in the Context of Homicide Prediction},
  publisher = {arXiv},
  year = {2022},
  copyright = {Creative Commons Attribution 4.0 International}
}
```
