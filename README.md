# Mall Customer Segmentation Using K-Means, DBSCAN, and PCA

## Project Overview

This project focuses on customer segmentation using unsupervised machine learning techniques. The Mall Customers dataset is used to group customers based on their age, annual income, and spending score.

Two clustering algorithms, **K-Means and DBSCAN**, are applied to the same scaled dataset to compare the customer groups they identify. Principal Component Analysis (PCA) is then used to reduce the data to two dimensions and visualize the clustering results using scatter plots.

## Objectives

- Prepare and scale numerical customer features.
- Determine a suitable number of clusters for K-Means using the Elbow Method.
- Apply K-Means clustering to segment customers.
- Apply DBSCAN to identify dense customer groups and potential noise points.
- Use PCA to reduce the data to two dimensions.
- Visualize and compare the clustering results from both algorithms.

## Dataset

**Dataset:** Mall Customers

The dataset contains customer demographic and spending information.

| Column | Description |
|---|---|
| `CustomerID` | Unique customer identifier |
| `Gender` | Customer gender |
| `Age` | Customer age |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Customer spending score |

For clustering, the following numerical features are selected:

- Age
- Annual Income (k$)
- Spending Score (1-100)

`CustomerID` is excluded because it is an identifier rather than a meaningful clustering feature. Gender is also excluded from this implementation.

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook / Google Colab

## Project Workflow

### 1. Data Loading and Inspection

Load the dataset using Pandas and inspect its structure, first few rows, dimensions, and missing values.

### 2. Feature Selection and Scaling

Select Age, Annual Income, and Spending Score as input features. Apply `StandardScaler` to standardize the features so that differences in numerical ranges do not disproportionately influence distance calculations.

### 3. K-Means Clustering and Elbow Method

Use the Elbow Method to evaluate different values of K by calculating the Within-Cluster Sum of Squares (WCSS).

The elbow plot indicates that **K = 4 is a reasonable initial choice** because the curve begins to flatten after approximately four clusters, although the elbow is not perfectly sharp.

Apply K-Means with four clusters and assign each customer a cluster label.

### 4. DBSCAN Clustering

Apply DBSCAN to the same scaled features. DBSCAN identifies groups based on point density rather than requiring a predefined number of clusters.

The `eps` and `min_samples` parameters control neighborhood distance and the minimum number of nearby points required to form a dense region. The parameters should be selected based on the k-distance plot and the resulting clustering behavior.

DBSCAN also identifies noise points using the label `-1`.

### 5. Dimensionality Reduction Using PCA

Apply PCA to transform the three scaled features into two principal components.

The two components are used as the x-axis and y-axis in scatter plots, allowing the clustering results to be visualized in two dimensions.

### 6. Cluster Visualization and Comparison

Create side-by-side scatter plots to compare K-Means and DBSCAN using the same PCA coordinates.

Compare the algorithms based on:

- Number of clusters identified
- Distribution of customers across clusters
- Separation and density of the groups
- Identification of noise points
- Suitability for the observed customer data

## Algorithms Used

| Algorithm | Purpose |
|---|---|
| K-Means | Divides customers into a predefined number of clusters |
| DBSCAN | Identifies dense groups and detects noise points |
| PCA | Reduces feature dimensions for visualization |
| Elbow Method | Helps select a suitable K for K-Means |
| StandardScaler | Standardizes numerical features |

## Expected Outcomes

This project demonstrates how unsupervised machine learning can be used to explore customer behavior and identify customer segments.

K-Means provides a fixed number of clusters, while DBSCAN can discover density-based groups and identify noise. PCA makes it possible to visually compare the groupings produced by both algorithms.

The final interpretation should be based on the actual cluster counts, scatter plots, and DBSCAN parameter settings obtained during execution.

## How to Run the Project

1. Clone or download this repository.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib scikit-learn jupyter
   ```

3. Place `Mall_Customers.csv` in the appropriate project directory.
4. Open the notebook in Jupyter Notebook or Google Colab.
5. Update the dataset path if necessary.
6. Run the cells in sequence.
7. Review the elbow plot, k-distance plot, cluster counts, and PCA scatter plots.

## Conclusion

This assignment applies two different unsupervised clustering algorithms to the Mall Customers dataset. Feature scaling supports a fairer distance-based comparison, the Elbow Method helps select the number of K-Means clusters, and DBSCAN provides an alternative approach based on data density. PCA enables both sets of cluster labels to be visualized in two dimensions.

The project provides practical experience with customer segmentation, clustering algorithms, dimensionality reduction, and exploratory data analysis.

## Skills Demonstrated

Python · Data Preprocessing · Feature Scaling · Unsupervised Machine Learning · K-Means · DBSCAN · PCA · Data Visualization · Customer Segmentation
