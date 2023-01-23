# Autors

José Ribeiro - site: https://sites.google.com/view/jose-sousa-ribeiro

Níkolas Carneiro - site: https://br.linkedin.com/in/nikolas-carneiro-62b6568

Ronnie Alves (Leader) - site: https://sites.google.com/site/alvesrco

# ConeXi

This is a library developed during the article "Black Box Model Explanations and the Human Interpretability Expectations - An Analysis in the Context of Homicide Prediction", by José Ribeiro, Nikolas Carneiro and Ronnie alves.

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
