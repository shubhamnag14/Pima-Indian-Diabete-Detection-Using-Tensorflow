# Pima-Indian-Diabete-Detection-Using-Tensorflow

This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases.The objective is to predict based on diagnostic measurements whether a patient has diabetes.
Several constraints were placed on the selection of these instances from a larger database. In particular,all patients here are females at least 21 years old of Pima Indian heritage.

<pre>Pregnancies: Number of times pregnant.
Glucose: Plasma glucose concentration a 2 hours in an oral glucose tolerance test.
BloodPressure: Diastolic blood pressure (mm Hg).
SkinThickness: Triceps skin fold thickness (mm)
Insulin: 2-Hour serum insulin (mu U/ml)
BMI: Body mass index (weight in kg/(height in m)^2)
DiabetesPedigreeFunction: Diabetes pedigree function
Age: Age (years)
Outcome: Class variable (0 or 1)
</pre>
Inspiration:
<pre>some values are not in the range where they are supposed to be, should be treated as missing value.
What kind of method is better to use to fill this type of missing value? How further clasification will be like?
Is there any sub-groups significantly more likely to have diabetes?
#feature range plotted below:
</pre>
Data Selection
<pre>Randomly picking up 700 total observations from 768 patients was finished in R. The new dataset was
named after PID.
</pre>
Predicting the probability to suffer from diabetes for individual females:
<pre>Generalize linear model contributed to solve this problem. In the glm, the binomial family was chosen,
since the response variable was only consisted of 1 and 0.
The generated model is:
REP=-0.8532997 + PRG*0.0211334 + PLASMA*0.0059682 - BP*0.0021338 + THICK*0.0005073 -
INSULIN*0.0002122 + BODY*0.0129676 + PEDIGREE*0.1361092 + AGE*0.0024004
Here, doing Cross-Validation checked Generalized Linear Model. The MSE (mean square of error) of this
model was 3.322.
What’s more, according to the Table 3, 5 variables (PRG, PLASMA, BP, BODY and PEDIGREE) had an
important influence on REP, since their P-Value of coefficient < 0.05.
Hence, the adjusted model was,
REP=-0.853 + PRG*0.0211 + PLASMA*0.00597 - BP*0.00213 + BODY*0.0130 + PEDIGREE*0.136
The next, doing Cross-Validation checked Generalized Linear Model. The MSE (mean square of error) of
this model was 2.952.
The MSE of adjusted model, 2.952, is less than that of whole model, 3.322.
Finally, the chosen model to predict the probability was:
REP=-0.853 + PRG*0.0211 + PLASMA*0.00597 - BP*0.00213 + BODY*0.0130 + PEDIGREE*0.136
The value of REP was taken as index to return the probability of suffering from diabetes for individual
females.
When the value of REP is close to 1, it means the individual female has higher probability to have diabetes.
When the value of REP is close to 0, it means the individual female has a healthy physical body.
The details were attached in Table 3.
</pre>
![](image/C:\Users\Shubham\Desktop)

