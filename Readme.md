# QML
## First Apporach
My first thought was to do basic Data Pre Processing as we do in Classical ML
1) Check if Data is Unbalanced
    - Since the Data set is Balanced no need to do anything, if it was unbalanced we would have balanced it using SMOTE to create synthetic points
 2) Check For Missing Values
    - Since there were no missing values, no need to do anything, if there were missing values we would have used some Imputation techniquies to handel it
3) Remove Outliers:
    - Remove Outliers: To avoice overfitting we ignore the outliers
4) Expolatory Data Analysis:
    - Using matplotlib plot all the features and check its distribution
5) Find Core-relation:
    - Using sns.heatmap plot the co-relation, I wanted to ignore Non Important features but without Domain Knowlege I decided to not do anything and consider everything
6) Develop a model using "QSVC" library  and "FidelityQuantumKernel" as kernel
    - The result I got shows highly overfitting which is not good

[First_Apporach.ipynb](First_Apporach.ipynb)

```
Classification Report for Training Data:
              precision    recall  f1-score   support

     Class 0       1.00      0.90      0.95       272
     Class 1       0.93      1.00      0.96       366

    accuracy                           0.96       638
   macro avg       0.96      0.95      0.95       638
weighted avg       0.96      0.96      0.96       638

```
```
Classification Report for Testing Data:
              precision    recall  f1-score   support

     Class 0       0.43      0.28      0.34        65
     Class 1       0.60      0.75      0.67        95

    accuracy                           0.56       160
   macro avg       0.52      0.51      0.50       160
weighted avg       0.53      0.56      0.53       160

```
## Second Approach
- From the first apporach I learnt that
    1) Taking all features result into overfitting
    2) My main problem was that it took me 1 hr to run the code once on my Macbook so I had to reduce the features if I want to try something new

- To reduce the complexity I decided to use PCA to reduce the NO of features
    1) This helped me reduce the Execution time, Now the code took only 30 min approximately
    2) I used "QSVC" Qiskit library and "TrainableFidelityQuantumKernel" as my kernel

[using_library.ipynb](using_library.ipynb)
```
Classification Report for Training Data:
              precision    recall  f1-score   support

     Class 0       0.65      0.50      0.57       532
     Class 1       0.58      0.71      0.64       508

    accuracy                           0.61      1040
   macro avg       0.61      0.61      0.60      1040
weighted avg       0.61      0.61      0.60      1040

Classification Report for Testing Data:
              precision    recall  f1-score   support

     Class 0       0.62      0.51      0.56       130
     Class 1       0.58      0.69      0.63       130

    accuracy                           0.60       260
   macro avg       0.60      0.60      0.60       260
weighted avg       0.60      0.60      0.60       260

```
## Third Apporach
- My goal was to mimic what I did in the 2nd Apporach without using pre-built Kernel.
 1) I used PCA to reduce the Number of features as done above
 2) Instead of using a prebuilt kernel I wrote a python function "quantum_kernel"
 3) The output I was got was identical to what I got in 2nd Approach
 4) Here I am using "statevector_simulator" for time being, I am not using probalistic simulator as done in above two cases

[usingKernel.ipynb](usingKernel.ipynb)

# Author
Sujeet Sanjay Amberkar