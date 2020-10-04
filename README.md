# PCA
# import data which contains numeric variables.

















import numpy as np 

import pandas as pd 

from numpy.linalg import eig 

variable = []

Pca = []

cors =[] 


def PCA(data):
    
    for i in data columns: 
        data[i] = data[i]-np.mean(data[i])
        Covariance_matrix=np.cov(data.T)
        values,vectors = eig(Covariance_matrix)
        P = vectors.T.dot(Data.T)
        PcA = pd.DataFrame(P.T)
    for i,j in zip(PcA.columns,range(0,PcA.shape[1],1)):
        PcA.rename(columns = {i:"PCA" +str(j)},inplace= True)
    for i in data columns:
        for d in PcA.columns:
            corrs = data[i].corr(PcA[d])
            cors.append(corrs)
            variable.append(i)
            Pca.append(d)
            correlation = pd.DataFrame(PcA.columns)
            from itertools import islice
            from itertools import repeat
            given_value = correlation.shape[0]
            length_to_split =[]
            length_to_split.extend(repeat(given_value, int(len(cors)/correlation.shape[0])))
            Input = iter(cors)
            Output = [list(islice(Input,elem)) for elem in length_to_split]
            for i,j in zip(data.columns, Output):
                ll= j
                correlation[i]=ll
     return(correlation.T)
              
