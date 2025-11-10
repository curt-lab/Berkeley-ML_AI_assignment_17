Practical Assignment 17 - README
For this assignment we followed the template provided, which was structured along the CRISP-DM framework.
The technical problem to be solved was to compare multiple models classification models to solve a business problem.  The models to be compared were Logistic Regression,
KNN (K-Near Neighbor), Decision Tree, and SVM (Support Vector Machines).
We were given a dataset from a telemarketing campaign to get banking clients to suscribe to a long-term deposit project from UCI (see https://archive.ics.uci.edu/dataset/222/bank+marketing).  NOTE: There was also supposed to be a link to a paper on the dataset, but that had been removed. 
The business objective was to determine if the particular client would be likely subscribe (Yes or No) to the product offer.
The goal would be to focus the telemarketing effort on clients who are predicted as likely to subscribe (Yes).
We were given a set of 20 features in the full dataset of over 41k samples (records).  Some features related to the client and past interaction with the client.  Some related 
to macro-economic factors likely to affect the clients decsion.  (See the variable description list in the junyper notebook)
We set a benchmark of 87% accuracy for the majority class (clients saying No to the offer).
Our models were able to beat that but not by a large margin.  We would probably need to do more feature engineering and data scraping to significantly improve that.
The most effective model in our testing was the Decision Tree classifier and it yielded around 89% accuracy on the test dataset.
The SVM model took a long time to train and did not initially offer significant improvement, so we did not explore that model beyond the initially required investigation.
The model did actually improve to just over 90% inferring which clients would say Yes when we included a feature called 'duration', however 'duration' was not 
really viable for a predictive model because it measured how long the client engaged with the telemarketer and that is something that could only be determined after a call
to the client was made.  Again, we are striving for a model to determine in advance (before a call) is the client likely to be say Yes to the offer.
The rest of the results are summarized below (also included in the junyper notebook:
Model Comparison Results:
                        Train Time	Train Accuracy	Test Accuracy	Best Params
KNN	                    5.236553	0.881511	0.883694	{'n_neighbors': 9}
Decision Tree	          0.397382	0.886884	0.890584	{'criterion': 'gini', 'max_depth': 6}
Logistic Regression	    2.956878	0.888811	0.888615	{'C': 0.01}

#OVERALL RESULTS:
#Decision Tree with the hyperparameters tuned per the chart above showed the best combination of training
#time and accuracy for training cross-validation set and test set.
#Running the models with default in Problem 10 yielded higher training accuracy scores than the optimized models
#in Problem 11 in some cases, but the test accuracy was lower, so there was some improvement.  Indicating the 
#default models were overfitting.
#The Decision Tree model would correctly predict the outcome (yes or no) 89% of the time.
#If I had more time perhaps to further clean data or try different sub-sets of the data I might have gotten a 
#different result.
