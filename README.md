# Cardiovascular_disease-dataset-binary-classification-models
This repository discusses the binary classification models (with hyperparameter tuning) with strategies to obtain the best performing models with the best performing model on the dataset.
<p>
<h2>Strategy used for arriving at the best performing binary classification problem model</h2>
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
<li> Logistic regression model is fit on features selected using the Feature selection techniques including f-test, mutual information and recursive feature elimination techniques</li>
<li> Hyperparameter selection of C (regularization term) and number of iterations is performed and model is fit with the best set of parameters.</li>
</li>
</ol>
<li> Support Vector Machines (SVM)
  <ol>
    <li> SVM with Linear Kernel (with default hyperparameters), with features selected using f-test, mutual information and Recursive feature elimination (RFE). Hyperparameter selected using validation curves. </li>
    <li> SVM with RBF kernel (with default hyperparameters), with features selected using f-test, mutual information and Recursive feature elimination (RFE). Hyperparameter selected using validation curves. </li>
  </ol>
  <li> Decision Trees
    <ol>
      <li> Decision Tree with default parameters, hyperparameter selected decision tree.</li>
        <li>Bagged decision trees, bagged decision trees with hyperparameter selected bagging parameters. </li>
    </ol>
  </li>
  <li> Random forest
    <ol>
      <li> Plain random forest, and hyperparameter selected random forest</li>
    </ol>
  </li>
  <li>Extra Trees classifier
    <ol>
      <li> Extra trees classifier, and hyperparameter selected Extra Trees classifier </li>
    </ol>
  </li>
  <li> K-nearest neighbor 
    <ol>
      <li> K-nearest neighbor with default parameters, and hyperparameter selected K nearest neighbor (Using rule of thumb of sqrt()).</li>
      <li> Bagged K-nearest neighbor with hyperparameter selected bagging parameters.</li>
    </ol>
  </li>
  <li> Multilayer perceptron (MLP)
    <ol>
      <li> Multilayer perceptron with default parameters and hyperparameter seleted MLP. </li>
    </ol>
  </li>
  <li> Gradient Boosted Trees (GBT)
    <ol>
      <li> GBT with default parameters, GBT with early stopping</li>
      <li> GBT with hyperparameter selection</li>
    </ol>
  </li>
  <li> Adaboost classifier 
    <ol>
      <li> Adaboost classifier with default base class with default parameters</li>
      <li> Adaboost classifier with SVM (with best hyperparameters) as the base class, and hyperparameter selction of boosting parameters. </li>
      <li> Adaboost classifier with Decision Trees (with best hyperparameters) as the base class, and hyperparameter selection of boosting parameters.</li>
    </ol>
  </li>
  <li> Voting ensamble classifier
    <ol>
      <li> Ensamble of classifiers Logistic Regression and Support Vector Classifier (with best hyperparameters selected before)</li>
    </ol>
  </li>
  </li>
</p>
</p>
  <h2> Requirements</h2>
  Scikit-learn 
  
  
  <h2>Note </h2>
  <ol>
    <li>In some classifiers, the validation curve is constructed using parameter 'cv' less than 10 as a result of lower compute power and time. Feel free to increase the value of cv if you have the compute time and power. </li>
    <li> Feel free to use other classifiers to build the voting classifier (ideally classifiers that make uncorrelated errors on samples make good candidates for voting classifier)</li>
    </ol>
  
    
  
