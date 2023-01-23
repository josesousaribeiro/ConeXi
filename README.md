# Autors

José Ribeiro - site: https://sites.google.com/view/jose-sousa-ribeiro

Níkolas Carneiro - site: https://br.linkedin.com/in/nikolas-carneiro-62b6568

Ronnie Alves (Leader) - site: https://sites.google.com/site/alvesrco

# ConeXi

This is a library developed during the article *"Black Box Model Explanations and the Human Interpretability Expectations - An Analysis in the Context of Homicide Prediction"*, by José Ribeiro, Nikolas Carneiro and Ronnie alves.

The main function of this library is to perform the combination of ranks, with or without loss of elements, in a final rank that represents the ideal combination of all ranks passed as input.

In a practical way, this library can be used to combine the output of several Explainable Artificial Intelligence - XAI measures aimed at the global explanation of black box models. Combining them or not, with output from human experts.

The possibility of using this library is varied, not limited to the XAI area.

# Intallation

```python
pip install ConeXi
```

# Import

```python
from combineranks import ConeXi
```

# Simple execution

In this example, 3 different ranks (rank1, rank2 and rank3) containing 5 elements (attributes) each will be combined into a single final rank.

This is the initial dataframe needed for execution:

```
  att_original_names rank1 rank2 rank3
0                 f1    f3    f4    f1
1                 f2    f4    f1    f2
2                 f3    f1    f2    f3
3                 f4    f2    f3    f4
4                 f5    f5    f5    f5
```

This is the python code:

```python
#Simple example of utilization of ConeXi
d = {'att_original_names': ['f1', 'f2','f3','f4','f5'], 
    'rank1': ['f3', 'f4','f1','f2','f5'],
    'rank2': ['f4','f1','f2','f3','f5'],
    'rank3':['f1','f2','f3','f4','f5']}
df = pd.DataFrame(data=d)
    
c = ConeXi(5)
    
rank_final, data = c.ExecuteConeXi(df)
    
print(rank_final)
```

This is the output of execution:

```python
att_original_names      
f1                  27.0
f4                  26.0
f3                  25.0
f2                  24.0
f5                  18.0
```

# Cite this work

You can cite the package using the following bibtex entry:
```
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
