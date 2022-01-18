# FinalProject
### Abstract:
The main purpose of any building, shed, or electrical permits is to ensure safety. By enforcing proper safety standards, you and other occupants of a space are guaranteed the best chance to avoid any accidents or issues during the construction process. In my project, I looked at construction data from the "Washington DC Construction permit dataset," which contains information on application requesting for permit in the city of Washington DC from the year 2017 to 2021.I looked at patterns over time, trends, and  corelation between variables using the matplotlib library. Encoding categorical variables, feature selection, data standardization, and scaling are performed as part of .The final phase is modeling, building machine learning algorithms to predict labels. The model must predict the "ISSUED" label in order to identify the possibility of the application getting through so that the chance of particular application to be rejected can be found in prior without the government officials taking much efforts. I want to identity permits that are likely to be not issued in order to provide real-time feedback to submitters and/or the staff reviewing the permits

### DataSet:
https://opendata.dc.gov/datasets/construction-permits-in-2020/explore?location=38.916792%2C-77.022175%2C11.73&showTable=true
Every record identifies a construction permits information using various features. These attributes include   X , Y, OBJECTID, APPLICATIONDATE, ISEXCAVATION, ISFIXTURE, ISPAVING,ISLANDSCAPING,ISPROJECTIONS,ISPSRENTAL ,TRACKINGNUMBER , PERMITNUMBER, INTAKEDATE, ISSUEDATE , EFFECTIVEDATE , EXPIRATIONDATE, XCOORD, YCOORD , STATUS, WLFULLADDRESS, PERMITTEENAME, OWNERNAME, CONTRACTORNAME, WORKDETAIL, READYFORREVIEWDATE, APPLICANTCOMPANYNAME, LATITUDE, LONGITUDE, GIS_ID, GLOBALID, CREATOR, CREATED, EDITOR,EDITED

### EDA and Data cleaning:
Check the data , info, null values ,removing the unique values , date values and imputable values. Grouping  status ‘Cancel/Withdrawn’, ‘Revise/Resubmit’, ‘Denied’, ’Suspended’, ‘Revoked’  into Not issued and Approved into Issued. Look for the coorelation between vairables , distribution of variables, check the geolocation coordinates , visualize them to see the distribution of issued and not issued.

### Feature engineering :
One hot encoding(OHE)  is a popularly used technique of categorical encoding. Here, categorical values are converted into simple numerical 1’s and 0’s without the loss of information.  
Rescaling of all values in a feature in the range 0 to 1

### Modeling:
Independent variables are analyzed to determine the binary outcome with the results falling into one of two categories. The independent variables can be categorical or numeric, but the dependent variable is always categorical in case of classification algorithms. Built logistic regression model , Decision trees and support vector classifer Machine learning models with  parameter tuning using grid search.Also built a sklearn neural network. 
Logistic Regression:
{'logreg__C': 100, 'logreg__penalty': 'l1', 'logreg__solver': 'liblinear'}
Support Vector Classifier:
{'svc__kernel': 'poly'}
Decision Tree:
{'tree__criterion': 'entropy',
 'tree__max_depth': 10,
 'tree__min_samples_leaf': 50}
 
### Results and discussion:

Logistic: ROC AUC=0.626
SVC: ROC AUC=0.711
Tree: ROC AUC=0.663
Neural Network: ROC AUC=0.714

Logistic Regression score:0.8117283686730506
Decision Tree score:0.85047024623803
Support Vector Classifier score:0.822935191518468
Neural Network score:0.8526995305164319

Regarding ROC AUC score , SVC and Neural network is more than other algorithms. Accuracy is better for Neural Network and Tree. More than any Machine Learning algorithms , Neural Network is better in regards with this data.
### Next steps:
    
More analysis with respect to four date fields in the dataset.                                       
Instead of just predicting two labels , (Issued and Not issued ) predict more specific class
### References:

https://github.com/appliedecon/data602-lectures

https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74

https://machinelearningmastery.com/roc-curves-and-precision-recall-curves-for-classification-in-python/

https://stackoverflow.com/questions/32370281/how-to-embed-image-or-picture-in-jupyter-notebook-either-from-a-local-machine-o
