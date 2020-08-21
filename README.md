# nami-jupiter-v1

**Description**

Jupiter provides stress prediction in case there is no calendar data available.  The focus is on the data collected from the previous versions of the app calendar data to predict the stress level of a new user. It is based on the aggregated features 

**Phase 1:**

***Previous app date Column Names:** firstName	email	Age	Gender	UserActivity_updatedAt	Stress Score*    

In this phase the preprocessing it self required prediction of age as well as gender of the users from their names and emails since the data was missing.Next was transitioning the date obtained from existing version of the app such that it could be modelled. I  extracted the Time of Day And Day of the week from 'UserActivity_updatedAt' and converted 'stress score' into stress level.  Hopefully when the app is launched none of this preprocessing would be required since we hope to obtain  at least the age and sexfrom the users when they join the app.



**Phase 2:**
***New  columns:** sex	age	Weekday	TimeOfDay	 StressLevel* 

Once I obtained the data in the above format, data modelling process involved smote oversampling and tuning parameters to obtain an accuracy of 72% using a Random Forest Classifier




**Details of Files Uploaded**


1. [modelx.csv](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/modelx.csv): This file contains the messy data obtained from the previous version of the app.
2. [PreprocessAgeGender.ipynb](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/PreprocessAgeGender.ipynb): This python file preprocess the data:
                    -Gender Prediction using [Gender Predictor Python package](https://github.com/clintval/gender-predictor)
                    -Age prediction based on email id domain of the users
                    -Extracting Time of the day(Morning/Noon/Eve/Night) from 'UserActivity_updatedAt' column
                    --Extracting weekday from 'UserActivity_updatedAt' column
3. [Preprocessed.csv](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/Preprocessed.csv)-This file contains all the preprocessed data genreted from [PreprocessAgeGender.ipynb](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/PreprocessAgeGender.ipynb) file
4. [FE1.ipynb](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/FE1.ipynb): This code groups the data on the basis of 'sex','Predicted_age','Weekday','TimeOfDay' to find average stress score for each group
5. [FE1.csv](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/FE1.csv): File generated from FE1.ipynb
6. [FE2.ipynb](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/FE2.ipynb): This code labels the mean stress score
7. [finaldata.csv](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/finaldata.csv): File generated from FE2.ipynb. This is the dataset that will used for modelling purpose
8. [model.ipynb](https://gitlab.com/mc-dev-team/build/back-end/mc-backend-prototypes/data-science-internships/jupiter-v1/-/blob/master/model.ipynb): Trains the Random Forest model using the final dataset with a final accuracy of 72%. This file is also **jupiter.py** but with user input allowed to test the model.

**Steps to Execute**


*NOTE:Most of the files I have uploaded are files related to converting the app data to the required features for building the model. This step wouldnt be necessary for the new app.*


1. Download finaldata.csv
2. Download model.pkl
3. Download jupiter.py
4. Keep the files in the same folder
5. In the cmd prompt go to the path where the folder is located and and execute `python jupiter.py`

**Here is how it looked for me:**


C:\Users\19792\Downloads>python jupiter.py

Enter Age :24

Enter Sex (M/F):F

['Great']


