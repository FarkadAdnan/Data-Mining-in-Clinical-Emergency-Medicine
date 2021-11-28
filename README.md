# Data-Mining-in-Clinical-Emergency-Medicine
Clinical databases can be categorized as huge data, and include large amounts of information about patients and their medical conditions. The project is that the dataset represents 10 years of clinical care in 130 hospitals and integrated delivery networks. Includes over 50 features representing patient and hospital outcomes. Information was extracted from the database of interviews that fulfilled the criteria.

## The first practice is the 130-year diabetes dataset 1999-2020
The dataset represents 10 years of clinical care in 130 hospitals and integrated delivery networks. Includes over 50 features representing patient and hospital outcomes. Information was extracted from the database for interviews that fulfilled the following criteria. The data contains attributes such as patient number, race, gender, age, type of admission, time in hospital, admission physician medical specialty, number of lab tests performed, HbA1c test result and diagnosis, number of medications and diabetes medications, number of outpatient, inpatient and emergency visits per year pre-hospital, etc.

(1) It is an inpatient meeting (hospital admission).
(2) It is anti-diabetic, i.e. any type of diabetes was introduced into the system as a diagnosis.
(3) The length of stay was at least one day and at most 14 days.
(4) Laboratory tests were carried out during the meeting.
(5) Medicines were administered during the encounter.

## This dataset is complicated and unbalanced. Let's do it!
![Figure_1](https://user-images.githubusercontent.com/35774039/143790736-3258785b-c08d-427d-be2b-70de77caba44.png)
there are three types of labels. We just regroup it to two labels.

`data['readmitted'] = pd.Series([0 if val == 'NO' else 1 for val in data['readmitted']])` 

Then we look at the feature:age, we visualize it by groups
![Figure_1](https://user-images.githubusercontent.com/35774039/143790760-61ccb5f6-6069-45ef-a1d3-1e3b9a9e0e6e.png)
We find it really unbalance,then regroup this feature.
![Figure_1](https://user-images.githubusercontent.com/35774039/143790782-1fbe636c-5dab-432b-a6a5-c7ff97e29110.png)
It is better now.

There are two many features in this dataset, but many of features are noisy. We use random forest to evaluate the importance of each features and rank them.
![Figure_1](https://user-images.githubusercontent.com/35774039/143790805-350d8b99-0944-46f8-9517-2ea59682f688.png)
Ok, we just select Top 10 features for the following procedure. We have washed this dataset and could apply our machine learning algorithm.

## Using k-means for clustering and ROC for evaluation
![Figure_1](https://user-images.githubusercontent.com/35774039/143790822-ba84e7ac-9bb8-4959-8b6a-6dfb7ed764ac.png)
![Figure_1](https://user-images.githubusercontent.com/35774039/143790838-0011a695-3d3d-4ce3-bb4e-1c916aa01ec9.png)


# The third practice is using SVM
The SVM is an important classify in machine learning, we need to practice how to use the SVC in sklearn lib. You can see all codes in SVM.py

First we create some fake data for classification
![Figure_1](https://user-images.githubusercontent.com/35774039/143791003-8659b991-2817-4b39-be45-c0fbae6645cd.png)
Then we use 10 fold cross validation to choose paramater gamma
![Figure_1](https://user-images.githubusercontent.com/35774039/143791022-df4daed1-19b1-4383-b2fc-68969f147b8a.png)
We can adopt SVC and draw the hyperplane
![Figure_1](https://user-images.githubusercontent.com/35774039/143791026-bbc407ad-476b-4209-82a7-a18a9013bb57.png)

To communicate with me:
 farkad.hpfa95@gmail.com




