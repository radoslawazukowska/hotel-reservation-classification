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

<img width="633" height="491" alt="Screenshot 2026-02-14 at 11 10 05" src="https://github.com/user-attachments/assets/1cb0cba2-9ff5-419c-bf59-f1540833b6e4" />

<img width="633" height="491" alt="Screenshot 2026-02-12 at 17 10 25" src="https://github.com/user-attachments/assets/fa9f7615-cc09-41d8-80b6-6ef16d3e5c62" />

<img width="633" height="491" alt="Screenshot 2026-02-12 at 17 11 03" src="https://github.com/user-attachments/assets/824ba623-d9c5-46e5-bd13-92ec0268fa86" />

<img width="633" height="491" alt="Screenshot 2026-02-14 at 11 10 35" src="https://github.com/user-attachments/assets/e3669c87-ef1f-4f29-9063-4fd5fa52d1bc" />

<img width="1031" height="421" alt="Screenshot 2026-02-14 at 11 11 11" src="https://github.com/user-attachments/assets/42b1d2c6-b329-4f34-a423-fcf71ea05cc6" />

## Model Selection
First, the dataset was split into three parts: training, validation, and test sets. The validation set was used for model selection, and after choosing the best-performing model, the training and validation sets were merged and used for final training. The final model performance was then evaluated on the test set.

We evaluated several types of models: Logistic Regression, Random Forest, Support Vector Classifier (SVC), and Gradient Boosting Classifier. Model performance was assessed using the classification report, which includes metrics such as accuracy, precision, recall, and F1-score. Additionally, we compared training and validation accuracy to check for overfitting.

<img width="451" height="210" alt="Screenshot 2026-02-14 at 11 22 46" src="https://github.com/user-attachments/assets/8c2a167a-bc3e-40c0-9439-b1dbccc569c5" />

<img width="451" height="210" alt="Screenshot 2026-02-14 at 11 23 02" src="https://github.com/user-attachments/assets/06ad637e-7bed-4a72-b589-396f22aa1914" />


Based on the validation metrics, Random Forest and SVC achieved the best performance. We then applied GridSearchCV to optimize the hyperparameters of both models. After tuning, we compared their performance using confusion matrices and ROC curves. Based on these evaluations, Random Forest was selected as the final model.

Finally, feature importance analysis showed that lead time and average price per room had the greatest impact on the model’s predictions.

<img width="477" height="439" alt="Screenshot 2026-02-14 at 11 20 45" src="https://github.com/user-attachments/assets/bedd70bf-4917-4668-97f4-10a5d4bc441b" />

<img width="477" height="439" alt="Screenshot 2026-02-14 at 11 21 45" src="https://github.com/user-attachments/assets/50e8dd1a-8347-4213-9d95-717b2aa76baf" />

<img width="701" height="463" alt="Screenshot 2026-02-14 at 11 21 11" src="https://github.com/user-attachments/assets/aba42f56-4402-41a1-ba0e-b0a85c88ac84" />

## Business Recommendations
1. Catering Optimization: Discontinue the underused Meal Plan 3 to streamline kitchen operations and cut costs. For Meal Plan 2, investigate quality issues or introduce non-refundable deposits due to its high cancellation rate.

2. Room Risk Management: While Room Type 1 drives volume, Room Type 6 poses the highest operational risk. I recommend implementing a stricter cancellation policy specifically for this category.

3. Loyalty Programs: Data shows returning guests are more reliable. We should prioritize loyalty programs, as new customer acquisitions currently carry a higher risk of cancellation.

4. Complimentary Bookings: With a 100% fulfillment rate, free stays are an excellent tool for guaranteed occupancy (e.g., for influencers, partners, or service recovery).

## Data Source
Data: *Hotel Reservations Dataset* by *AHSAN RAZA* (Kaggle), licensed under **CC BY 4.0**.
https://www.kaggle.com/datasets/ahsan81/hotel-reservations-classification-dataset

