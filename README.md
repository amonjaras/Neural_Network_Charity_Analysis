# **Neural Network Charity Analysis**
Module 19: Neural Networks and Deep Learning Models

## **INDEX**

- **[Overview](#overview)**

- **[Results](#results)**

- **[Summary](#summary)**


## **Overview**
Beks has come a long way since her first day at that boot camp five years ago—and since earlier this week, when she started learning about neural networks! Now, she is finally ready to put her skills to work to help the foundation predict where to make investments.

With knowledge of machine learning and neural networks, we’ll use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, we received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

- **EIN** and **NAME**: Identification columns
- **APPLICATION_TYPE**: Alphabet Soup application type
- **AFFILIATION**: Affiliated sector of industry
- **CLASSIFICATION**: Government organization classification
- **USE_CASE**: Use case for funding
- **ORGANIZATION**: Organization type
- **STATUS**: Active status
- **INCOME_AMT**: Income classification
- **SPECIAL_CONSIDERATIONS**: Special consideration for application
- **ASK_AMT**: Funding amount requested
- **IS_SUCCESSFUL**: Was the money used effectively

For this Challenge, we'll need to perform the analysis as the following:

- Processing Data for a Neural Network Model
- Compile, Train, and Evaluate the Model
- Optimize the Model

[:top: Go To Top](#index)

## **Resources**

### **Data**

- [Charity Dataset](https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/Resources/charity_data.csv)

### **Tools**

- Neural Network and Deep learning
- Python: Pandas
 - Tensorflow
 - ScikitLearn
- Jupyter Notebook

[:top: Go To Top](#index)

## **Results**

1. **Processing Data**

✅  **[AlphabetSoup]**(https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/AlphabetSoupCharity.ipynb)

Below the remarks for this point:

- Variables dropped: `EIN` and `NAME`
- Target Variable: `IS_SUCCESSFUL`
- Target Accuracy: `75%`
- We will optimize other columns if needed.

2. **Compile, Train and Evaluate Model**

- Number of inputs: `len(X_train[0])`
- Hidden nodes: `2` with neurones of `80` and `30` respectively.
- Activation functions: `relu` and `sigmoid`
- Number of epochs: `100`

**Was this model able to achieve the target?**

The model was not able to achieve the target of **75%**. The result of this evaluation is **72.6%**

![model](https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/Images/model.png)

3. **Optimize the model**

We performed 3 attempts to optimize the model and improve the accuracy as follows:

#### **Attempt 1**

✅  **[Optimized1]**(https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/AlphabetSoupCharity_Optimization.ipynb)

1. **Processing Data**

Below the remarks for this point:

- Variables dropped: `EIN`, `NAME`, `USE_CASE`, `ORGANIZATION`, `STATUS`
- Target Variable: `IS_SUCCESSFUL`
- Target Accuracy: `75%`

2. **Compile, Train and Evaluate Model**

- Number of inputs: `len(X_train[0])`
- Hidden nodes: `3` with neurones of `100`, `60` and `40` respectively.
- Activation functions: `tanh`, `relu` for layer1 and layer2, and `sigmoid`
- Number of epochs: `100`

**Was this model able to achieve the target?**

The model was not able to achieve the target of **75%**. The result of this evaluation is **72.3%**

![att1](https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/Images/opt1.png)

#### **Attempt 2**

✅  **[Optimized2]**(https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/AlphabetSoupCharity_Optimization2.ipynb)

1. **Processing Data**

Below the remarks for this point:

- Variables dropped: `EIN`, `NAME`, `USE_CASE`, `ORGANIZATION`, `STATUS`
- Target Variable: `IS_SUCCESSFUL`
- `APPLICATION_TYPE` count decreased to 500
- Adding `INCOME_AMT` and `ASK_AMT` to the binning
- Target Accuracy: `75%`

2. **Compile, Train and Evaluate Model**

- Number of inputs: `len(X_train[0])`
- Hidden nodes: `3` with neurones of `100`, `60` and `40` respectively.
- Activation functions: `tanh`, `relu` for layer1 and layer2, and `sigmoid`
- Number of epochs: `100`

**Was this model able to achieve the target?**

The model was not able to achieve the target of **75%**. The result of this evaluation is **72.3%**

![att2](https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/Images/opt2.png)

#### **Attempt 3**

✅  **[Optimized3]**(https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/AlphabetSoupCharity_Optimization3.ipynb)

1. **Processing Data**

Below the remarks for this point:

- Variables dropped: `EIN`, `NAME`, `USE_CASE`, `ORGANIZATION`, `STATUS`
- Target Variable: `IS_SUCCESSFUL`
- `APPLICATION_TYPE` count changed to 500
- `CLASSIFICATION_TYPE` count changed to 500
- `INCOME_AMT` count changed to 500
- `ASK_AMT` count changed to 900
- Adding `INCOME_AMT` and `ASK_AMT` to the binning
- Target Accuracy: `75%`

2. **Compile, Train and Evaluate Model**

- Number of inputs: `len(X_train[0])`
- Hidden nodes: `4` with neurones of `200`, `100`, `50` and `25` respectively.
- Activation functions: `relu`, `tanh`, `linear`, `relu` for layers 1 to 4, and `sigmoid` for output
- Number of epochs: `200`

**Was this model able to achieve the target?**

The model was not able to achieve the target of **75%**. The result of this evaluation is **72.5%**

![att3](https://github.com/amonjaras/Neural_Network_Charity_Analysis/blob/main/M19_Challenge/Images/opt3.png)


[:top: Go To Top](#index)

## **Summary**

After performing 3 attempts optimizing the data, the model was not able to achieve 75% accuracy target.

The average in all the attempts continue to be 72%. It is interesting that in all the attempts the losses are around 55% and could be interpreted as the model to be overfitted.

For the model to reach the expected accuracy we recommend to use Random Forest Classifiers, since is robust and accurate model due to the sufficient number of estimators and tree depth. They also have faster performance than Neural Networks.

[:top: Go To Top](#index)



This work belongs to [^1].
Course [^2].
[^note]:
[^1]: Author: Audrey MONJARAS :mexico: :panama: :canada:
[^2]: Data Analytics: Unit 19 Neural Networks
