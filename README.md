# Cancer Type Classification Based on RNA-seq Data Using Machine Learning

This report presents multiple machine learning approaches to classify cancer based on gene expression data obtained through RNA-seq. The gene expression data was used to train a machine learning model on a dataset consisting of various types of cancer. The results of this report suggest that machine learning can be an effective tool for classifying patients suffering from cancer by analyzing the gene expression matrix.

## Data_Base

This study's dataset is an extensive, multivariate collection of real-life gene expression measurements from 801 patients, each diagnosed with one of five specific cancer types: Colon Adenocarcinoma (COAD), Kidney Renal Clear Cell Carcinoma (KIRC), Breast Cancer (BRCA), Lung Adenocarcinoma (LUAD), and Prostate Adenocarcinoma (PRAD). The data is organized into two files: "data.csv" contains the gene expression matrix, while "labels.csv" details the cancer classification of each patient. With data representing 20,531 genes, this dataset is a cornerstone for our supervised learning approach, where pre-labeled data with specific cancer acronyms guides the model training and validation process.
We used the database on : [gene expression cancer RNA-Seq](https://archive.ics.uci.edu/dataset/401/gene+expression+cancer+rna+seq).

## Data_Preprocessing

In our study, data preprocessing commenced with the aggregation of datasets and their corresponding labels. A thorough cleaning was conducted by checking all rows with missing values. Detailed checks revealed and led to the elimination of duplicate columns, including an unnamed column. A descriptive analysis was carried out to assess data distribution. For outlier management, we employed the Interquartile Range (IQR) method, removing columns with a high percentage of outliers, based on a predefined threshold (3%) to maintain data quality. chose to remove data with outliers instead of imputing them for two key reasons. Firstly, we are working with real data, and employing imputation methods could potentially alter the original dataset's integrity. Secondly, given the large number of columns in our dataset, managing outliers through removal seemed a more practical approach to preserve the dataset's authenticity and maintain manageable data dimensions. Finally, columns containing only zeros were identified and removed as they contributed no significant information, thus refining our dataset for analysis.

## Feature_Selection

Following the univariate analysis of the target variable and its distribution. We implemented a statistical approach to determine the significance of each variable in relation to the target variable. Since we have non-normally distributed data, we used the KRUSKAL-WALLIS test, a non-parametric alternative to the ANOVA, particularly useful in scenarios where the data has a normal distribution. We set a significance threshold at 0.05. For each variable in our dataset. Variables that did not show statistically significant differences across these groups were considered to have minimal influence on the target variable and were thus identified as non-significant and removed. 

## Data_Balancing

In our study, we addressed the issue of class imbalance in the dataset using the Synthetic Minority Over-sampling Technique (SMOTE). This technique augmented our dataset by generating synthetic samples for under-represented classes. By doing so, we achieved a more balanced class distribution, which is crucial for avoiding bias towards majority classes in machine learning models.

## UMAP

In the dimensionality reduction section of our study, we initially employed a correlation matrix to assess the interrelationships among variables. This analysis revealed complex, multi-dimensional patterns, underscoring the need for a sophisticated approach to reduce dimensionality without significant loss of information. Consequently, we chose UMAP (Uniform Manifold Approximation and Projection), an advanced non-linear dimensionality reduction technique. UMAP's ability to preserve both the global and local structure of data made it an ideal choice, allowing us to effectively compress our dataset into a lower-dimensional space while retaining the essential characteristics of the original high-dimensional data.

## Data_Normalization & Data_Split

For data normalization, we utilized the StandardScaler to standardize the training data, ensuring that our features had a mean of zero and a standard deviation of one. The same scaler was then applied to the test data to maintain consistency between the datasets. We split our data into training and testing sets in an 80:20 ratio, ensuring a substantial amount of data for model training while reserving a fair portion for model.
## Model's_Algorithms

In our research, we implemented three distinctive machine learning models: SVM, XGBoost, and ANN, to compare their efficacy. The SVM model was chosen for its proficiency in handling high-dimensional data, while XGBoost was employed for its superior performance in classification tasks, with its robustness validated through cross-validation techniques. Additionally, an ANN model was deployed to discern complex patterns within the data, undergoing extensive training. The primary objective of utilizing these diverse models was to evaluate and compare their performance thoroughly, thereby determining the most effective approach for our dataset analysis.

## Keywords: 
Machine Learning, Deep Learning, UMAP, ANN, XGBoost, SVM.


