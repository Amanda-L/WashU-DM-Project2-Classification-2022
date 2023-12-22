# Washu_datamining_project_2_2022
Project 2: Implemented various models (KNN, SVM, Decision Tree, Random Forest, ANN, Naïve Bayes Classifier) with dimension reduction techniques for binary and multiclass classification tasks.

# Information on the files

## Programming Assignment 2.pdf: 

The project used a dataset from the Letter Recognition dataset in the UCI repository. It has 20,000 samples of 26 alphabets with each alphabet having 16 features. 

In the problem, I picked from different models (1. k-nearest neighbors, 2. Decision tree, 3. Random Forest, 4. SVM, 5. Artificial Neural Network, and 6. Naïve Bayes Classifier) to do binary classification. For each model, I chose a hyperparameter to tune using 5-fold cross-validation. 

I compared different models in terms of their performance. By looking at the appearance of letters, I have a pre-sense of how certain letters are harder to classify. For instance, D and Q would make models harder to classify. I also tried clustering after dimension reduction, to see whether reducing features dimension impacts the results.


## SP2023 Project 2 Code .ipynb and Project 2 Final Report.pdf: 
These are the codes for the whole project and written reports documenting the whole process.

# Discussion and Main Findings:

## Motivation for multiple classifiers. What factors should be considered in determining a classifier as the “best”?

When evaluating a model, I prioritize several key factors, including computational complexity, validation accuracy, and model interpretability. However, I also take into account the model's ability to generalize to new data and its robustness to noise. It's important that the computation cost of a model does not outweigh its value, and that it performs better than the average. A good model should be intuitive and not too far removed from common sense. Additionally, it's crucial that the model doesn't overfit the training data and can handle variations in the data without being overly sensitive. Meeting these criteria is hard, but it determines the best model.

## Motivation for dimension reduction. Which methods are “better,” and what factors should be considered in determining a dimension reduction method as “good” or “bad.”

The motivation behind dimension reduction is to simplify data by reducing the number of variables or features while retaining as much important information as possible. A good dimension reduction method should be computationally efficient and scalable while preserving the relevant information and discarding the irrelevant or redundant information. On the other hand, a bad method would not achieve these traits, such as being inefficient or discarding too much important information.

## Brief description of the dimension reduction method(s) I chose.
I chose Principal Component Analysis (PCA) to do feature extraction. PCA is able to transcribe data into lower dimensions by projecting onto the principal components, which are linear combinations of the original variables that capture the most variation in the data. I suppose it can capture and retain most information of the data while doing dimension reduction.

## Speculate on the binary classification problems. Which pair of letters did I choose for the third problem? Which pair do I predict will be the easiest or hardest to classify?
I chose A and B, because they look the least similar to each other. I have also considered T and Y, or K and O, which are all letter pairs that are easy to distinguish. Harder pairs would be D and Q, O and Q, or E and F, which are pairs that are sometimes also hard for humans to distinguish if with limited information.

## Discuss the advantages/disadvantages of using a multi-class classifier instead of a set of binary classifiers.
The advantages of using a multi-class classifier include a simplified training process and potentially better results. This is because multi-class classifiers can input multiple data samples at the same time, which is simpler than using a single binary classifier. Possibly better results are because of its ability to look at multiple correlations between features and leverage them. However, a disadvantage of using a multi-class classifier is that it takes longer to compute compared to a single binary classifier. Additionally, the results of a multi-class classifier may be harder to interpret, as the multiplication of layers is more complicated than with binary classifiers.

## For each classifier, provide a brief description of the classifier and its general advantages and disadvantages.
For KNN, it can handle classification and regression problems and is also simple to implement and fairly easy to interpret. However, it is sensitive to how I choose the distance metrics, which will be seen in more hyperparameter tuning.

For ANN, it can compute more complex problems with different relationships between features. It can also handle unstructured data fairly well. However, it is prone to overfit when the model gets too complicated, therefore also making it hard to interpret. Also, the most obvious downside is it takes the longest to train.

For SVM, it can handle both linear and non-linear data because of its nature of projecting data into higher dimensions to find solutions. However, choosing the right kernel may be tricky and it is sensitive to the choice of hyperparameters.

For Random Forest, it is easy to interpret when having a small dataset, and it is relatively less prone to overfitting. However, when the dataset gets larger, it takes a pretty long time to train and is hard to interpret, I have tried to print out the first few forests, but it was indeed hard to comprehend.

## What model would I choose for this problem and why? How did dimension reduction affect the accuracy and/or run times of the different classifiers? What would I do differently if I were given this same task for a new dataset? Include at least one additional topic of discussion.

For the first topic, the focus is on dimension reduction. In general, models that use dimension reduction tend to achieve testing accuracy of around 50-60%, which is considered relatively poor. This could be due to overfitting during the training phase, as many models perform very well with training accuracies over 95%, but generalize poorly during testing. In my experience, using dimension reduction can reduce the overall computation time, but the reduction may not be significant. This could be because the dataset used was not sufficiently large or complex, and fewer hyperparameters were required to achieve optimal results.
The second topic would be on the run time, ANN took the longest to train and is prone to overfitting. If I could choose based on the results of the assignments, I would choose KNN, then probably SVM. Given that KNN is fairly easy to interpret and takes less time to train.


