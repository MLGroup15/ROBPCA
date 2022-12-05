
# ROBPCA: A New Approach to Robust Principal Component Analysis

> Mia Hubert, Peter J Rousseeuw & Karlien Vanden Branden (2005) ROBPCA: A New Approach to Robust Principal Component Analysis, Technometrics, 47:1, 64-79, DOI: 10.1198/004017004000000563




**Birla Institute of Technology and Science, KK Birla Goa Campus : Machine Learning BITS F464 - Group 15**

_Honor Code: We shall be honest in our efforts and will make our parents proud._


Shikha Bhat (2019A7PS0063G)

Yash Trivedi (2019B4AA0834G)

Viraj Sharma (2020A7PS1011G)



## Submission Files

- The presentation can be found [here](https://github.com/MLGroup15/ROBPCA/blob/main/ROBPCA_MLGroup15.pdf).
- The data can be found [here](https://github.com/MLGroup15/ROBPCA/tree/main/data).
- The code can be found [here](https://github.com/MLGroup15/ROBPCA/tree/main/src).
- The drive folder containing all necessary files can be found [here](https://drive.google.com/drive/folders/1Tw-O5lpdLiXRSnPVlCSGm3JpTtiv-LKm?usp=sharing).

Following is a summary of the paper,


## Motivation

While solving any ML problem, the data that we use to analyze and feed to the model is of great importance. Principal Component Analysis is widely used for the analysis of high-dimensional data, and allows us to represent the dataset as linear combinations of the original variables in a lower dimension. 

PCA often allows for interpretation and better understanding of the different sources of variation. However, the classic approach to PCA is sensitive to outliers (very high or low observations), because it is dependent on the variance-covariance matrix. The first principal component of a set of p variables is the derived variable formed as a linear combination of the original variables that explains the **most** variance. 

Outliers increase the variance of the data. The principal components may then be distorted so as to fit the outlier, which leads to a bad interpretation of the results. Thus, the authors of this paper aim to introduce a new, robust method of PCA, which can address this problem. They call it ROBPCA.


## Problem Definition

1. To develop a robust method through which we can accurately apply PCA to high dimensional data having outliers 
2. Using this robust PCA, get a diagnostic plot that can be used to detect and classify  outliers.


## Methodology

### The ROBPCA Method
Previous efforts have been to replace the classical covariance matrix by robust covariance estimators but these cannot resist many outliers or are limited to small to moderate dimensions. Projection pursuit techniques have also been used in the past, which can handle higher dimensions. The ROBPCA method attempts to combine the advantages of both approaches - 
1. The projection pursuit technique is used for the initial dimension reduction of the data.
2. Some ideas based on the MCD estimator (minimum covariance determinant) are then applied to this lower-dimensional data space. 


### Diagnostic Plots (Outlier Maps)

Diagnostic plots help in distinguishing between regular observations and three types of outliers - orthogonal outliers, good leverage points and bad levarage points by plotting the orthogonal distance of the outliers from the PCA subspace vs the robust score distance of the observations.


## Results and Discussion
The study analyzes several real datasets from chemometrics and engineering, and compares the results from ROBPCA with four other PCA methods. For simplicity, here we summarize in a table how the ROBPCA method compares to Classical PCA - 


| Dataset       | Dimensions (training examples x features) | No. of components retained | Results                                                                                                                                                                                                                                              |
| ------------- | ----------------------------------------- | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Car           | 111 x 11                                  | 2  |  Both CPCA and ROBPCA detected same set of outliers, but the subspace found by CPCA is attracted toward the bad leverage points.                                                                                                                      |
| Octane        | 226 x 39                                  | 2                     | ROBPCA was able to detect 6 outliers, while CPCA detected only 1.  |
| Glass Spectra | 750 x 180                                 | 3                                       |   CPCA does not find important outliers. ROBPCA clearly distinguishes 2 major groups in the data, a smaller group of bad leverage points, a few orthogonal outliers, and 1 isolated case.                                                             |

## Conclusion

In this study, the authors construct a fast and robust algorithm to apply PCA on high dimensinal data. They apply PP techniques and these results are used to project the observations on smaller dimension subspace. Within this subspace we apply ideas of robust covariance estimation. Applications on real datasets show that the algorithm gives robust estimates even when data contains outliers. The associated outlier maps are very useful to visualize and classify the different outliers. The ROBPCA method thus opens a door to practical robust multivariate calibration and to the analysis of regression data with both outliers and multicollinearity. 

