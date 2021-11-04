# HeartDiseasePrediction
PREDICTING THE TEN YEAR RISK OF DEVELOPING HEART DISEASE USING MACHINE LEARNING


Heart attacks are mainly caused by cardiovascular diseases (CVDs). CVDs refers to the set of the heart and blood vessels disorders such as: coronary heart disease, cerebrovascular disease, peripheral arterial disease, rheumatic heart disease.
The aim of this project is to use clinical diagnosis data (Framingham dataset ) as an input to predict whether a patient has 10 years risk of developing coronary heart disease as an output using SVM (Support Vector Machine), Random forest and ANN algorithms with the best accuracy and performance.

The methodology steps for this project proposed as follow:


![image](https://user-images.githubusercontent.com/53998396/140255517-1d66dd64-6169-4af9-8061-90605f9e315c.png)


 

1-	Data Frame:     The data has been collected from Kaggle using Framingham dataset.

2-	Exploratory Data Analysis: 

2-1 The dataset include 4240 record and 15 attribute. The target variable is the ten years risk of coronary heart disease and it showed in the 
dataset as binary where 1 means YES and 0 means NO.

Attributes:

•	Sex: male or female
•	Age: Age of the patient
•	Education: no information provided
•	Current Smoker: whether or not the patient is a current smoker
•	Cigs Per Day: the number of cigarettes that the person smoked on average in one day
•	BP Meds: whether or not the patient was on blood pressure medication 
•	Prevalent Stroke: whether or not the patient had previously had a stroke 
•	Prevalent Hyp: whether or not the patient was hypertensive 
•	Diabetes: whether or not the patient had diabetes 
•	Tot Chol: total cholesterol level 
•	Sys BP: systolic blood pressure 
•	Dia BP: diastolic blood pressure 
•	BMI: Body Mass Index 
•	Heart Rate: heart rate 
•	Glucose: glucose level 


2-2 Missing data:  Glucose with 388 missing data is the highest. Education 105, cigsPerDay 29, BPMeds 53, TotalChol 50,BMI 19, HeartRate 1 missing data.


2-3 Correlation: The correlation explain the relation between variable. The education and CigPerDay have no or min relation with the target 
therefore these two attribute have been dropped.


3-	Data Preparation and Pre-processing:

3-1. Handling missing data: As the dataset is small therefore instead of deleting the missing data, I replace the missing data with the mean
value.

3-2. Handling imbalance data:  The dataset shows 3596 records with no CAD risk and 644 records with CAD. As we can see the two classes are
imbalance. All machine learning algorithm designed based on equal number of classes therefore imbalance data could result in poor performance
of the model. To overcome this problem I used SMOT technic.
 SMOTE (Synthetic Minority Oversampling Technique) create new samples for minority class using k-nearest neighbours. After applying SMOT there
 are 3595 with no CAD and 2876 record with CAD .
 
 ![image](https://user-images.githubusercontent.com/53998396/140255811-2607d1cf-da7c-4c8e-b250-8d8af5c9f5d4.png)


3-3. Feature selection: I used  Random forest Regressor to rank the important features in relation to the target variable and then reduce the
number of features.

![image](https://user-images.githubusercontent.com/53998396/140255914-29c64d90-0531-4c0f-a4cb-2bc1b9c693ed.png)

 
The 7 most important features has been selected 1. Age 2. Total cholesterol 3. Systolic blood pressure 4. Diastolic blood pressure 5. BMI 6.
Heart rate 7 Blood glucose

3-4. Feature scaling is a technic used to normalize the range of independent variables or features of data. The main reason of using this
method is to speed up the computation.

4-	Model training : Three classification models considered to be used are SVM, Random forest and ANN

4-1. Model tuning:  To find best parameter for each of the three models, I used Grid Search algorithm.

5-	Evaluation and comparison: The accuracy and F1 score of each model has been evaluated 


![image](https://user-images.githubusercontent.com/53998396/140255947-a685bdc6-2a58-4c46-9832-a1d7d014473c.png)


               
As above table shows , Random forest has best performance in term of accuracy and F1 .

5-1 Validation: K-Fold validation technic has been used to make sure that overfitting has not been occurred.

6-	Save the best model:  The trained Random forest model has been saved in Jason format. This trained model can be used to predict 10 years 
risk of the CAD for any new patient and we no longer need the existing data.
