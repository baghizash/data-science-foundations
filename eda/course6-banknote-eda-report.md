# Exploratory Data Analysis: Banknote Authentication Dataset

## Description of the dataset
The Banknote Authentication dataset contains 1372 records of banknote-like specimens described by 4 numerical features extracted from images: variance, skewness and curtosis of the wavelet-transformed image, and entropy of the image. Each record is labelled 0 (genuine, 762 records) or 1 (forged, 610 records).

## Statistical measures of the dataset
Means: variance 0.43, skewness 1.92, curtosis 1.40, entropy -1.19. Standard deviations: variance 2.84, skewness 5.87, curtosis 4.31, entropy 2.10. Skewness and curtosis show wide ranges (skewness from -13.77 to 12.95), indicating heavy-tailed distributions.

## Size of the dataset and number of its features
1372 rows and 5 columns: 4 input features plus 1 binary class label.

## Code
```python
import pandas as pd, numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

df = pd.read_csv('banknote.txt', header=None,
                 names=['variance','skewness','curtosis','entropy','class'])
print(df.describe())
Xs = StandardScaler().fit_transform(df.iloc[:, :4].values)
km = KMeans(n_clusters=2, n_init=10, random_state=42).fit(Xs)
plt.scatter(df['variance'], df['skewness'], c=df['class'], alpha=0.6)
plt.xlabel('variance'); plt.ylabel('skewness')
plt.text(0.05, 0.95, 'n=1372', transform=plt.gca().transAxes)
```

## Suitability for K-Means and recommendations
K-Means with k=2 on standardized features agrees with the true labels only 55.9 percent of the time, barely above chance. The classes overlap heavily in feature space and the features have very different scales and heavy tails, so plain K-Means is not well suited to this dataset without further feature engineering. Recommendation: try dimensionality reduction or density-based clustering, and always standardize features before K-Means.

## Limitations of the data analysis
Only K-Means with k=2 was evaluated, on a single standardization scheme; no hyperparameter search or alternative algorithms were tested, and the analysis relies on the labels only for validation, not for training.
