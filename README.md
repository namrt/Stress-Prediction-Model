# nami-jupiter-v1

**Description**

Jupiter provides stress prediction in case there is no calendar data available.  The focus is on the data collected from the previous versions of the app calendar data to predict the stress level of a new user. It is based on the aggregated features 

**Details of Files Uploaded**


1. [modelx.csv](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/modelx.csv): This file contains the messy data obtained from the previous version of the app.
2. [PreprocessAgeGender.ipynb](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/PreprocessAgeGender.ipynb): This python file preprocess the data:
                    -Gender Prediction using [Gender Predictor Python package](https://github.com/clintval/gender-predictor)
                    -Age prediction based on email id domain of the users
                    -Extracting Time of the day(Morning/Noon/Eve/Night) from 'UserActivity_updatedAt' column
                    --Extracting weekday from 'UserActivity_updatedAt' column
3. [Preprocessed.csv](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/Preprocessed.csv)-This file contains all the preprocessed data genreted from [PreprocessAgeGender.ipynb](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/PreprocessAgeGender.ipynb) file
4. [FE1.ipynb](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/FE1.ipynb): This code groups the data on the basis of 'sex','Predicted_age','Weekday','TimeOfDay' to find average stress score for each group
5. [FE1.csv](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/FE1.csv): File generated from FE1.ipynb
6. [FE2.ipynb](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/FE2.ipynb): This code labels the mean stress score
7. [finaldata.csv](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/finaldata.csv): File generated from FE2.ipynb. This is the dataset that will used for modelling purpose
8. [model.ipynb](https://gitlab.com/namrta.singh/nami-jupiter-v1/-/blob/master/model.ipynb): Trains the Random Forest model using the final dataset with a final accuracy of 72%

**Steps to Execute**
1. PreprocessAgeGender.ipynb
2. FE1.ipynb
3. FE2.ipynb
4. model.ipynb 