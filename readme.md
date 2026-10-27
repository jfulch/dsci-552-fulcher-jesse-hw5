# DSCI 552 - Homework 5

- **Name:** Jesse Fulcher
- **GitHub Username:** `jfulch`
- **Notebook:** [Fulcher_Jesse_HW5.ipynb](./notebook/Fulcher_Jesse_HW5.ipynb)
- **Assignment:** [Homework5.pdf](./Homework5.pdf)
- **Instructor:** Mohammad Reza Rajati

## Assignment Questions

## 1. Decision Trees as Interpretable Models

### 1(a). Download the Data

Download the [Acute Inflammations data](https://archive.ics.uci.edu/ml/datasets/Acute+Inflammations).

### 1(b). Build and Plot a Decision Tree

Build a decision tree on the whole data set and plot it.[^1]

### 1(c). Extract IF-THEN Rules

Convert the decision rules into a set of IF-THEN rules.[^2]

### 1(d). Cost-Complexity Pruning

Use cost-complexity pruning to find a minimal decision tree and a set of
decision rules with high interpretability.

## 2. The LASSO and Boosting for Regression

### 2(a). Download and Split the Data

Download the [Communities and Crime data](https://archive.ics.uci.edu/ml/datasets/Communities+and+Crime).[^3]
Use the first 1495 rows of data as the training set and the rest as the test
set.

### 2(b). Handle Missing Values and Nonpredictive Features

The data set has missing values. Use a data imputation technique to deal
with the missing values in the data set. The data description mentions some
features are nonpredictive. Ignore those features.

### 2(c). Correlation Matrix

Plot a correlation matrix for the features in the data set.

### 2(d). Coefficient of Variation

Calculate the coefficient of variation \(CV\) for each feature, where

\[
CV = \frac{s}{m},
\]

in which \(s\) is the sample standard deviation and \(m\) is the sample
mean.

### 2(e). Scatter Plots and Box Plots

Pick \(\lfloor \sqrt{128} \rfloor\) features with the highest \(CV\), and
make scatter plots and box plots for them. Can you draw conclusions about
the significance of those features just from the scatter plots?

### 2(f). Least-Squares Linear Regression

Fit a linear model using least squares to the training set and report the
test error.

### 2(g). Ridge Regression

Fit a ridge regression model on the training set, with \(\lambda\) chosen
by cross-validation. Report the test error obtained.

### 2(h). LASSO With and Without Standardization

Fit a LASSO model on the training set, with \(\lambda\) chosen by
cross-validation. Report the test error obtained, along with a list of the
variables selected by the model. Repeat with standardized[^4] features.
Report the test error for both cases and compare them.

### 2(i). Principal Component Regression

Fit a PCR model on the training set, with \(M\), the number of principal
components, chosen by cross-validation. Report the test error obtained.

### 2(j). L1-Penalized Gradient Boosting

In this section, we would like to fit a boosting tree to the data. As in
classification trees, one can use any type of regression at each node to
build a multivariate regression tree. Because the number of variables is
large in this problem, one can use L1-penalized regression at each node.
Such a tree is called an L1-penalized gradient boosting tree. You can use
XGBoost[^5] to fit the model tree. Determine \(\alpha\), the regularization
term, using cross-validation.

## Assignment Notes

[^1]: This data set is a multi-label data set. Scikit-learn seems to support
    building multi-label decision trees. Alternatively, you can use the label
    powerset method to convert it to a multiclass data set. Also, you can use
    the binary relevance method and build one decision tree for each label.
    It seems that the label powerset approach is more relevant here. Is that
    right?

[^2]: You can use the code in
    [Simplifying Decision Tree Interpretation with Decision Rules in Python](https://www.kdnuggets.com/2017/05/simplifying-decision-tree-interpretation-decision-rules-python.html).

[^3]: Question you may encounter: I tried opening the data set and downloading
    it, but the file is not readable. How do I download the file? Just change
    `.data` to `.csv`.

[^4]: In this data set, features are already normalized.

[^5]: Some hints on
    [installing XGBoost on Windows](http://www.picnet.com.au/blogs/guido/2016/09/22/xgboost-windows-x64-binaries-for-download/).