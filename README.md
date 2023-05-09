# deep_learning_analysis

## Overview

As a data analyst, one of my primary responsibilities is to develop a tool that enables enterprises to make precise decisions. In this project, I made a tool for Alphabet Soup, a nonprofit foundation using deep learning to  optimize a binary calssifier that predicts the likelihood of an applicant's success if funded by Alphabet Soup. This model was training by a csv file that contains more than 34,000 organizations that have previously received funding from Alphabet Soup. To improve the accuracy of the model's predictions, I also utilized some evaluation techniques and modified the model accordingly.

* Descriptions of the Dataset Columns:
    * EIN and NAME : Identification columns
    * APPLICATION_TYPE : Alphabet Soup application type
    * AFFILIATION : Affiliated sector of industry
    * CLASSIFICATION : Government organization classification
    * USE_CASE : Use case for funding
    * ORGANIZATION : Organization type
    * STATUS : Active status
    * INCOME_AMT : Income classification
    * SPECIAL_CONSIDERATIONS : Special considerations for application
    * ASK_AMT : Funding amount requested
    * IS_SUCCESSFUL : Was the money used effectively




## Results

* Data Preprocessing (Q & A):

    * What variable(s) are the target(s) for the models?

        Both of the original and optimized models are trained using 'IS_SUCCESSFUL' as the target variable.

    * What variable(s) are the features for the models?

        The feature variables in the original model excluded the 'EIN', 'NAME', 'IS_SUCCESSFUL' columns, and included all other columns.
        To improve the accuracy of the tool, in the optimized model, I included the 'NAME' column as one of the feature variables.

    * What variable(s) should be removed from the input data because they are neither targets nor features?

        Typically, 'EIN' and 'NAME' should be removed, but for improving prediction accuracy, 'NAME' may be included as a feature variable.


* Compiling, Training, and Evaluating the Model (Q & A):

    * How many neurons, layers, and activation functions did you select for your neural network model, and why?

        For the original model, I chose to include two hidden layers. The first hidden layer had 20 neurons, calculated by dividing the number of columns by 2 (45 columns / 2 almost equals to  20), and the second layer contained 10 neurons (20 / 2 = 10). In both layers, I used the 'relu' activation function.

        For the optimized models, I chose to include three hidden layers. The first two layers' structure is same as the original model and the third layer contained 5 neurons (10 / 2 = 5). In all these layers, I used 'relu' activation function.

        For the ouput layer of both original and optimized models,  I chose sigmoid function, as it is commonly used for binary classification tasks.

    * Were you able to achieve the target model performance? What steps did you take in your attempts to increase model performance?
    
        The initial target predictive accuracy of the model was 0.7318, which did not meet the required standard. To improve the model's performance, I included "NAME" as one of the feature variables, added an extra hidden layer, and increased the number of epochs.


![Accuracy of the Original Model Across Epochs](https://github.com/cycy94777/deep_learning_analysis/blob/main/image/accuracy.png?raw=true)

After optimizing the model, the target predictive accuracy increased to 0.7541, slightly above 75%. Therefore, we could conclude that the model now meets the required guideline.

![Accuracy of the Optimized Model Across Epochs](https://github.com/cycy94777/deep_learning_analysis/blob/main/image/opt_plot.png?raw=true)


## Summary

The main differences between the original and optimized models include adding the 'NAME' feature variable, an additional hidden layer, and increasing the number of epochs. These optimization methods have increased the model's predictive accuracy from 0.7318 to 0.7541, meeting the 75% guideline.
However, including 'NAME' as a feature variable may potentially impact fairness in the model. 
In situations where fairness is crucial, such as in certain legal or ethical contexts, it may be more appropriate to use the original model. On the other hand, if maximizing predictive accuracy is the primary objective and fairness concerns are less pressing, then the optimized model may be more appropriate. 