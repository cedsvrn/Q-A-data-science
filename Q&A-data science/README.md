# Q&A
Q&A questions about data science.


## Standardisation vs Normalisation
*Standardization is another scaling technique where the values are centered around the mean with a unit standard deviation. This means that the mean of the attribute becomes zero and the resultant distribution has a unit standard deviation.*

*Normalization is a scaling technique in which values are shifted and rescaled so that they end up ranging between 0 and 1. It is also known as Min-Max scaling.*

- Normalization is good to use when you know that the distribution of your data does not follow a Gaussian distribution. This can be useful in algorithms that do not assume any distribution of the data like K-Nearest Neighbors and Neural Networks.
- Standardization, on the other hand, can be helpful in cases where the data follows a Gaussian distribution. However, this does not have to be necessarily true. Also, unlike normalization, standardization does not have a bounding range. So, even if you have outliers in your data, they will not be affected by standardization.
However, at the end of the day, the choice of using normalization or standardization will depend on your problem and the machine learning algorithm you are using. There is no hard and fast rule to tell you when to normalize or standardize your data. You can always start by fitting your model to raw, normalized and standardized data and compare the performance for best results.

https://www.analyticsvidhya.com/blog/2020/04/feature-scaling-machine-learning-normalization-standardization/
https://towardsdatascience.com/normalization-vs-standardization-quantitative-analysis-a91e8a79cebf


## Collaborative filtering vs Content based
Goal : recommend a product P to a user A

- Collaborative filtering (CF) : Try to  find similar user to A and recommend what those users consumes.
Cons : Cold start (need user-item interactions), algorithms not standards.
- Content based (CB) :  Regroup products and recommend products close to P. 
Pros : Classification problem.
