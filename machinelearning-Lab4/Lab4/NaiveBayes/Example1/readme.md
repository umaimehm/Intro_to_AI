Naive bayes algori uses bayes theorm for conditional probability with a naive assumption that the features are not correlated to each other and tries to find conditional probability of target variable given the probabilities of features. We will use adult dataset here and using naive bayes classifier find out accuracy of income of adults. We use sklearn library and python for this machine learning. MultinomialNB is the classifier we use to train our model. There are other classifiers such as GaussianNB.
For more details on Naive Bayes Classifiers and its details.<br />
 https://www.quora.com/What-is-the-difference-between-the-the-Gaussian-Bernoulli-Multinomial-and-the-regular-Naive-Bayes-algorithms

 In this example we will use Naive bayes Alogorithm to check Accuracy of Naive Bayes Algorithm over ADULT dataset.We will follow these steps in this example.<br /><br />
1)Firsly we will load dataset and drops unrelated columns from dataset. <br /><br />
2)Next we will Defining features and output.<br /><br />
3)Afterwards we Spliting dataset into training and testing data.We will splits the dataset into 80% train data and 20% test data. After that we are going to train the model from this training data and once the model is trained then we test it on the testing data.<br /><br />
4) We will import the Naive Bayes Algorithm from the sklearn library. After that, we have trained our model on the training data( 80% of the total dataset which we split earlier) and the final step is to make predictions on the dataset using testing data(20% of the total dataset).<br /><br />
5)For evaluating an algorithm, confusion matrix, precision, are the most commonly used metrics which we have imported from sklearn library. The last Lines will print the evaluation metrics classification matrix, and accuracy score.<br /><br />
