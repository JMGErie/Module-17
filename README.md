# Module-17
This is the homework associated with Module 17 of the Berkeley AI/ML class

The website and dataset outline the pressing business challenge faced many banks and other businesses: the need to optimize the efficiency of directed marketing campaigns for bank deposit subscriptions amidst a backdrop of declining effectiveness in traditional mass campaigns. With response rates dwindling, directed marketing offers a promising avenue but is hindered by challenges like privacy concerns and the necessity for meticulous contact selection. 
To tackle this, this issue, I am employing CRISP-DM methodology, leveraging the more concise “bank” data set with all 17 columns being a random subset from the larger data set due to limited computing power and resources. In addition, using a smaller dataset accommodates the use of SVM as the latter performs significantly better on smaller data set. The goal is to develop predictive models capable of discerning the key attributes driving customer subscription behavior. Ultimately, in the real world, this work would help refine marketing campaign targeting, optimize resource allocation, and ultimately boost the success rates of deposit subscription endeavors.
Throughout the process, Grid Search Cross Validation is employed on Logistic Regression Decision Trees, K-Nearest Neighbors, and Support Vector Machines to construct predictive models tailored to the nuances of bank direct marketing. The overarching nature of the approach allows for model refinement, concise codes. This technique also ensuring the best hyperparameters that capture the intricacies of the data, customer behavior and campaign dynamics, are chosen. 
Assumptions:
•	The dataset, bank-additional.csv, with 10% of the examples (4119), randomly selected from 1), and 20 inputs is representative of the larger dataset (bank-additional-full).
•	“bank-additional” dataset mirrors the save data imbalance as the fuller dataset and the feature weights are the same, meaning there was no data treatment.
•	The column “duration” was discarded to have a more realistic predictive model as suggested by the authors.
Data Analysis:
The Baseline model was constructed. The results indicate that the model always predicts the majority class, but it fails to predict any instances of the minority class. 
Baseline Model Metrics:
Accuracy: 0.890507404709881
Precision: 0.0
Recall: 0.0
F1-score: 0.0
While the baseline model achieves a high accuracy by always predicting the majority class, it performs poorly in terms of precision, recall, and F1-score, particularly because it fails to capture any instances of the minority class. This underscores the importance of developing a more sophisticated model that can effectively predict both classes.
Simple Logistic Regression Model:
A simple logistic regression model with max_inter = 1000 was built and exhibited test accuracy of approximately 90.29% and a train accuracy of about 90.19%, indicating consistent predictive ability across both training and unseen test data. Despite a runtime of approximately 3509.41 seconds, its precision score of 0.625 reflects its capability to correctly identify positive outcomes around 62.5% of the time, while the recall score of 0.183 suggests it captures approximately 18.35% of actual positive instances. The F1 score of 0.284 underscores a balanced trade-off between precision and recall. 

More Complicated Models:
The table summarizing the outcomes: Accuracy (Test), Precision, Recall and F1 scores along with the associated model average fitting times of different machine learning models on a classification task, evaluated using various metrics thru grid search cross validation. the models used consist of are K-Nearest Neighbors (KNN), Logistic Regression, Decision Tree, and Support Vector Classifier (SVC) 
                
Model		       train score	test score	avg. fit time 	Precision	Recall 	F1 Score                                            
KNN                             0.90	0.896           	16.372                 0.525 		0.192     0.282
Logistic Regression   0.904   	0.904          	2.504   		0.656 		0.193  	 0.298  
 Decision Tree            0.909    	0.897         	14.768   	0.529   		0.248  	0.337 
SVC                    	        0.332    	0.237        	94.255  		0.615   		0.147  	0.237 

Please see code for a better view of the table

Training and Test Scores:
   - The KNN, Logistic Regression, and Decision Tree models have high training scores (around 0.9), indicating a good fit on the training data.
   - However, the test scores for KNN and Decision Tree are slightly lower (around 0.89-0.9), suggesting some overfitting to the training data.
   - Logistic Regression has similar training and test scores (around 0.9), indicating good generalization.

Fit Time:
   - Logistic Regression has the fastest average fit time (2.504), making it computationally efficient for training.
   - SVC has the slowest average fit time (94.255), which might be a concern for large datasets or real-time applications.

Precision and Recall:
   - Logistic Regression has the highest precision (0.656), indicating a relatively low false positive rate.
   - KNN, Decision Tree, and SVC have lower precision scores, ranging from 0.525 to 0.615.
   - All models have low recall scores (below 0.25), suggesting a high false negative rate, which might be a concern depending on the problem context.

F1 Score:
   - The Decision Tree model has the highest F1 score (0.337), providing a balance between precision and recall.
   - KNN and Logistic Regression have lower F1 scores (around 0.28-0.3), indicating a lower overall performance.
   - SVC has the lowest F1 score (0.237), suggesting it might not be the best choice for this problem.

Based on these results, Logistic Regression could be a good choice for the marketing campaign, considering its high precision, good generalization, and computational efficiency. However, if a better balance between precision and recall is desired, the Decision Tree model might be a better option, despite its slightly longer fit time. Considering the balance between performance, computational efficiency, and interpretability, the Logistic Regression model appears to be the best choice among the options provided.
In the Logistic Regression’s Lift Curve, with 10 bins, we observe varying degrees of improvement in response rates across segments. The values indicate that some segments experience a modest uplift (e.g., around 7.8% and 4.9%), while others demonstrate a more substantial increase (e.g., around 18.4% and 46.6%). Overall, the lift curve suggests that the campaign has the potential to significantly enhance response rates, particularly in certain targeted segments, thereby improving the efficiency and effectiveness of the marketing strategy.

Findings:

The analysis sheds light on optimizing bank marketing campaigns for deposit subscriptions, addressing a critical challenge faced by banks and businesses. The Logistic Regression model emerges as the most favorable choice among the four evaluated models, exhibiting superior performance on unseen data with a test (accuracy) score of 0.903. Notably, the model achieves a commendable balance between precision and recall, essential for accurate identification of positive and negative instances. Its relatively low average fit time of 2.5sec underscores its computational efficiency, facilitating swift model training. Furthermore, the interpretability of the Logistic Regression model offers valuable insights into feature importance, aiding in understanding customer behavior dynamics.

Next Steps and Recommendations:

Moving forward, it is advisable to validate the models on the complete dataset to potentially refine hyperparameters and ensure optimal model development. Subsequently, deploying the Logistic Regression model in real-world marketing campaigns, if it remains the top performer, can capitalize on its predictive accuracy and efficiency. Leveraging insights from the model, tailored marketing strategies can target potential customers more effectively, optimizing resource allocation while boosting subscription rates. Continuous monitoring and refinement based on new data will be pivotal to adapt to evolving customer trends and market dynamics. Additionally, exploring additional features and refining data collection processes holds promise for enhancing the model's predictive power and driving long-term campaign success.
