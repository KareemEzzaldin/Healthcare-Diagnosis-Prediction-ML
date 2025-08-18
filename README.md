# Healthcare-Diagnosis-Prediction-ML
In this project I built a machine learning pipeline that included:
- Preprocessing patient admission data with feature engineering
- Encoding categorical variables and scaling numerical ones
- Training a Random Forest classifier and using LIME for interpretability

The model reached an accuracy of only 33%. At first this looked like a model problem, but a deeper look at the dataset revealed the real issue.

What I learned from the dataset:
- The classes (Normal, Abnormal, Inconclusive) are well balanced, so imbalance isn’t the cause of low accuracy
- Many features such as Doctor, Hospital, and Insurance Provider are IDs with no medical meaning, which add noise rather than signal
- Stay Duration was miscalculated because of duplicated date fields, so a potentially useful feature was lost
- Most importantly, the dataset doesn’t contain strong clinical predictors (like vitals, lab results, or patient history) that usually drive diagnostic accuracy

Because of this, no matter what model I tried, performance stayed around 33%, which is the same as random guessing across three classes.
The key takeaway for me: good data is more important than complex models. Without features that truly connect to the outcome, even the best models can’t perform well.
This project gave me valuable experience in understanding the limits of machine learning when the data itself is the bottleneck.
