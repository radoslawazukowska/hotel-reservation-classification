# Hotel Reservation Project
## Description
The goal of this project is to analyze hotel booking data to identify key patterns and correlations related to reservation cancellations. The project aims to evaluate multiple machine learning models and select the most effective one for predicting whether a hotel booking will be canceled.
## EDA
### Conclusions from 'object' data
1. Meal plan type 3 was selected very rarely, while meal plan type 2 had the highest cancellation rate.
2. Room type 1 was the most frequently booked, but room type 6 showed the highest cancellation rate.
3. There is a correlation between guest repetition and cancellation rates — non-repeated guests are more likely to cancel their reservations.
4. Complimentary reservations were never canceled.
5. The incorrect date 29/02/2018 was corrected to 28/02/2018.
6. The highest number of cancellations occurs in June and July.
7. There was an increase in cancellations in 2018 compared to 2017.
### Conclusions from numeric data
1. There is a correlation between lead time and the cancellation rate — reservations with longer lead times are more likely to be canceled.
2. Room type 7 is the most expensive room type.
3. In September and October 2017, the average room rate increased significantly.

<img width="600" height="468" alt="Screenshot 2026-02-14 at 11 10 05" src="https://github.com/user-attachments/assets/1cb0cba2-9ff5-419c-bf59-f1540833b6e4" />

<img width="551" height="458" alt="Screenshot 2026-02-14 at 11 10 35" src="https://github.com/user-attachments/assets/e3669c87-ef1f-4f29-9063-4fd5fa52d1bc" />

## Model Selection
First, the dataset was split into three parts: training, validation, and test sets. The validation set was used for model selection, and after choosing the best-performing model, the training and validation sets were merged and used for final training. The final model performance was then evaluated on the test set.

We evaluated several types of models: Logistic Regression, Random Forest, Support Vector Classifier (SVC), and Gradient Boosting Classifier. Model performance was assessed using the classification report, which includes metrics such as accuracy, precision, recall, and F1-score. Additionally, we compared training and validation accuracy to check for overfitting.

Based on the validation metrics, Random Forest and SVC achieved the best performance. We then applied GridSearchCV to optimize the hyperparameters of both models. After tuning, we compared their performance using confusion matrices and ROC curves. Based on these evaluations, Random Forest was selected as the final model.

Finally, feature importance analysis showed that lead time and average price per room had the greatest impact on the model’s predictions.
## Data Source
Data: *Hotel Reservations Dataset* by *AHSAN RAZA* (Kaggle), licensed under **CC BY 4.0**.
https://www.kaggle.com/datasets/ahsan81/hotel-reservations-classification-dataset
