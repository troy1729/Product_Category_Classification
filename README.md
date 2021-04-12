# Product_Category_Classification

Dependencies:
Pandas: 1.1.5 
Numpy: 1.19.5 
nltk: 3.2.5 
tensorflow: 2.4.1 
keras: 2.4.3 
sklearn: 0.22.2.post1

Cleaning & Processing Data:
>> Product name and description combined is chosen as the feature.
>> NaN rows are removed from the data.
>> Primary category is segregated from the product category tree.
>> Every character except alphabets are substituted with a space followed by lower casing the sentences and stemming.
>> Categories are visualised and top 10 categories are chosen for the classification task to avois imbalanced dataset problem and keeping the task feasible.
>> Rows other then top 10 categories hace are removed from the data.

Model building and Training:
>> Multinomial Naive Bayes Classifier is used initially to classify the data.
>> Preapared data is first tokenized and then converted to matrices using TF-IDF vectorisation method.
>> Labels are encoded and also converted to binarized for further score calculations.
>> LSTM-DNN classifier wth pre trained word embeddings is used as the second model for the task.
>> Here tokenized data is converted to sequences first and then using glove embedding is assigned with a particular integer value to feed into the model.
>> Embedding layer followed by two LSTM layers with dropout and one fully connected layer with dropout and output layer. Due to binarized labels output layer is kept with 10 nodes as the number of classes.

Matrices and results:
>> Naive Bayes Classifier: Average Test Accuracy: 0.9846
                           Average AUC Score: 0.9979
>> LSTM-DNN: Average Test Accuracy: 0.9792
             Average AUC Score: 0.9991

Improvement Factor:
Other data processing techniques and vectorisation techniques can be used though both the models according to matrices reading are of production level. 1DCNN-LSTM models can also be experimented with other then that gradient boosting methods can also be proved to be a good choice. On the top of all these suggestions hyperparameters including no. of layers can be experimented with to work on the accuracy score.
