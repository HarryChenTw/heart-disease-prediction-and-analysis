# Heart Disease Prediction and Analysis using Random Forest
This is a simple prediction of heart disease using Machine Learning technique which is Random Forest here. Then we analysis each attribute to see which is more informative for model. Hope it can provide some information for further medical research.

## Data
Data is from [UCI](https://archive.ics.uci.edu/ml/datasets/Heart+Disease) and they also published on [kaggle](https://www.kaggle.com/ronitf/heart-disease-uci). If you need more information about each attribute, you can check on those websites. 

## Data Processing
For some attribute that is not ordinal, such as chest_pain_type, rest_ecg, st_slope, thalassemia, the value in these columns indicate a specific type. So we transform these attributes into dummy attribute or called one-hot representation.
Then we split to train and test set in ratio 0.8, 0.2
## Model
We've tried several models. The performance is in below table. As the RF yield the most accurate prediction, we pick RF as our analysis model.

| Model         | Accuracy      |
| ------------- |:-------------:|
| KNN |73.77%|
| SVM(linear SVC)|83.61%|
| Logistic Regression|86.25%|
|Navie Bayes|86.89%|
|**Random Forest**|**90.16%**|
### Prediction Result
In RF model, we evaluate in several metrics listed in below.

| Metric         | Score      |
| ------------- |:-------------:|
|Accuracy|0.9016|
|Sensitivity|0.9231|
|Specificity|0.8857|
|AUROC|0.9264|

ROC curve:
![ROC](/output_img/roc.png)

## Result Explination
### Feature Importance
![Feature Importance](/output_img/feature_importance.png)

### Permutation Importance
![Permutation Importance](/output_img/permutation_importance.png)

### Patrial Dependency Plot
Feature importance and permutation importance can only tell us which attribute is more important for model to predict. We cannot know this attribute increase or decrease the probability of having heart disease.
chest_pain_type_typical_angina :<br />
<img src="/output_img/pdp_chest_pain_type_typical_angina.png" width="800">

num_major_vessels :<br />
<img src="/output_img/pdp_num_major_vessels.png" width="800">

thalassemia_fixed_defect :<br />
<img src="/output_img/pdp_thalassemia_fixed_defect.png" width="800">

st_depression :<br />
<img src="/output_img/pdp_st_depression.png" width="800">
