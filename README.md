# Heart_UCI-dataset-binary-classification-models
This repository discusses the binary classification models (with hyperparameter tuning) with strategies to obtain the best performing models with the best performing model on the dataset.
<p>
<h2>Strategy used for arriving at the best performing binary classification problem.model</h2>
<ol>
<li> The dataset is split into training (80%) and test dataset (20%). Validation is performed using k-fold cross validation, wherein the train dataset is split into 
k equal samples and training is performed on k-1 sample sets and validation on one. All k sets will serve as validation set once. </li>
<li> The features are reviewed. It can be seen that the categorical features in this case are cardinal in nature (indicating quantity), so they are simply label encoded (and not one-hot encoded).</li>
<li> The continuous features are scaled</li>
<li> The following classifiers are fit on the training dataset, validation performance (mean and standard deviation), area under the Precision-Recall curve and the area under the ROC curve is extracted:
<ul>
<li> Logistic regression
<ol>
<li> Plain logistic regression is fit using scikit-learn's deafult parameters (and hyperparameter selected parameters).</li>
<li> Logistic regression model is fit on features selected using the Feature selection techniques including f-classification, mutual information and recursive feature elimination techniques</li>
<li> Hyperparameter selection of C (rregularization term) and number of iterations is performed and model is fit with the best set of parameters.</li>
</li>
</ol>
<li> Support Vector Machines (SVM)






</p>
