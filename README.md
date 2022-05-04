
﻿
# <center>**Karmalife Assignment Solution**</center>

----
# **Table of Contents**
----

**1.**  [**Problem Statement**](#section1)<br>

**2.**  [**Importing Packages**](#section2)<br>

- **2.1**  [**Installing and upgrading Libraries**](#section201)<br>

- **2.2**  [**Importing Libraries**](#section202)<br>

  

**3.**  [**Loading Data**](#section3)<br>

**4.**  [**Data Exploration**](#section4)<br>

- **4.1**  [**Description of the Dataset**](#section401)<br>

- **4.2**  [**Data Information**](#section402)<br>

- **4.3**  [**Pre-Profiling Report**](#section403)<br>

  

**5.**  [**Data Preprocessing**](#section5)<br>

- **5.1**  [**Treating missing values**](#section501)<br>

- **5.2**  [**Treating duplicate values**](#section502)<br>

- **5.3**  [**Treating outliers**](#section503)<br>

  

**6.**  [**Exploratory Data Analysis**](#section6)<br>

**7.**  [**Data Post-processing**](#section7)<br>

**8.**  [**Modelling and Evaluation**](#section8)<br>

**9.**  [**Conclusion**](#section9)<br>


<a  name=Section1></a>
---
# **1. Problem Statement:-**

----

  

Assignment: Predict the probabilities of default

-------------------------

  

1)Develop a data-driven credit risk model to predict the probabilities of default (PD)

  

2)Can you assign credit scores to existing or potential borrowers

  
  

Your submission will be evaluated on the following points:

  

● Data and modelling abilities along with the choice metrics

  

● Data Presentation skills
<a  name = Section2></a>

## **2. Installed & Imported Libraries**

<a  name = Section31></a>

### **2.1 Installed Libraries**

- For starters, we installed the `pandas_profiling` library which gives a quick, general overview of the dataset.
- Additionally, we have installed the `datascience` library that is required by pandas profiling library.

<a  name = Section32></a>
### **2.2 Imported Libraries**

The following libraries and tools were used for the project:
<center><img  src="https://cdn.analyticsvidhya.com/wp-content/uploads/2020/11/Untitled-design24.png"  width=80%></center>

- **Pandas**: Importing for panel data analysis
- **Pandas Profiling**: To perform data profiling
- **Numpy**: For numerical python operations
- **Matplotlib (Pyplot)**: A popular plotting library used along with pandas
- **Seaborn**: A library, built on matplotlib, to create beautiful plots
- **Scikit Learn**: To perform all tasks realted to Machine Learning





<a  name = Section3></a>

## **3. Data Pre-processing Steps**

<a  name = Section41></a>

### **3.1 Dataset Description**:

<center>


- We have **466285 Samples**  and for each of sample **74 different** properties are recorded.
-  In order to get the complete Data Dictionary click **<a href="https://github.com/ghoshpronay18071997/karmalife_Ai_Solution/blob/main/Data%20Dictionary.xlsx">here </a>**

</center>


### **3.2 Data Cleaning**

- In this section, we **cleaned out** our data based on the information retrieved from the previous observations.

- Hence, we performed the following subtasks.

- Checking for **missing values** and manipulating them.

- Checking the **datatype**.

- For **categorical features** we replaced the null values with their corresponding modes, as mode returns the highest frequency recorded.

- For  **continuous features** we replaced the null values with their corresponding mean value.

- We also **dropped the unwanted features** that could not be treated further.

-  These features had **>90%** of **missing data** and hence, no further information could be retrieved from them.
<a name=Section4></a>

## **4. Insights from the EDA**

<center><img  src="https://cdn-images-1.medium.com/max/1000/1*Owa2rsDG6Rwv1IM_RdsL3A.gif"></center>

- To get the observations of the **numerical features** click **<a href="https://github.com/ghoshpronay18071997/karmalife_Ai_Solution/blob/main/numerical_obs.csv">here </a>**

- To get the observations of the **categorical features** click **<a href="https://github.com/ghoshpronay18071997/karmalife_Ai_Solution/blob/main/categorical_obs.csv">here </a>**

- We saw that the following features are sensitive to outliers.

- Hence, we will be following the list of methods to treat them

| Feature Name | Treatment | Reason for Treatment selection method |
| --: | :-- | :-- |
| int_rate | NA | We can see that this feature has not too many outliers. hence, performing transformation / cappimng out data may result in data loss. Hence, we will keep this feature as it is |
| installment | cap out method | We will try caping out the outliers and check the amount of data loss |
| annual_inc | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| delinq_2yrs | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| inq_last_6mnths | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| mnths_since_last_deling | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| mnths_since_last_record | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| open_acc | cap out method | We will try caping out the outliers and check the amount of data loss |
| pub_acc | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| revol_bal | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| revol_util | cap out method | We will try caping out the outliers and check the amount of data loss |
| total_acc | cap out method | We will try caping out the outliers and check the amount of data loss |
| out_prncp | cap out method | We will try caping out the outliers and check the amount of data loss |
| total_payment | cap out method | We will try caping out the outliers and check the amount of data loss |
| total_payment_inv | cap out method | We will try caping out the outliers and check the amount of data loss |
| total_payment_prncp | cap out method | We will try caping out the outliers and check the amount of data loss |
| total_payment_inv | cap out method | We will try caping out the outliers and check the amount of data loss |
| total_rec_int | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| total_rec_late_fee | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| recoveries | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| collection_recovery_fee | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| tlast_payment_amnt | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| collections_l2_mnths_ex_med | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| mnths_since_last_major_derog | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| acc_new_delinq | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| tot_coll_amt | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| tot_cur_bal | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| tlast_payment_amnt | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |
| total_rev_hi_lim | log transformation | The data is highly right skewed. Hence, need to perform log transformation and perform a quality check |

- After perfroming log transformaton there is no significant improvement for **delinq_2yrs**, **total-rec_late_fee**, **recoveries**, **collection_recovery_time**, **total_rev_hi_lim**.

- In this case we leave it as it is because there will be too much of data loss if we cap them out or drop them.

## **5. Data Postprocessing**

- In this section we performed the **Data Encoding**.

- We saw that there was **class imbalance** in the **target feature.**

- In order to get the correct class balance we will be using **oversampling** technique using **SMOTE**.

- Then we further used **oversampling** method to treat the **class imbalance**.

- Three sets of data were made in order to get the best fit. 
- We tried with the following approach:
	- **`Set 1 -- > Oversampled Data`**
	- **`Set 2 --> simple data correlation`**
	- **`Set 3 --> Data Correlation + Oversampled Data`**


- Next we performed **Data Extraction**.


<a name=Section6></a>
## **6. Modelling and Hyoeroparameter Tuning and Prediciton**
<center><img  src="https://cdn.dribbble.com/users/1571442/screenshots/6356637/dribbbble_machinelearning_4x.png"></center>

- We performed modelling with most of the commonly used **Machine Learning** models.

-  As a **Baseline** it was found that **Random Forest Classifier** was giving us the highest **accuracy** and least **overfitting**.

- however, due to **class imabalance**, we would also consider **Precision** , **Recall**, **TPR** and **FPR**


<center><img src="https://github.com/ghoshpronay18071997/karmalife_Ai_Solution/blob/main/Metrics/Metrics_1.png"></center>


<center><img src="https://github.com/ghoshpronay18071997/karmalife_Ai_Solution/blob/main/Metrics/Metrics_2.PNG"></center>



<center><img src="https://github.com/ghoshpronay18071997/karmalife_Ai_Solution/blob/main/Metrics/Metrics_3.PNG"></center>

- We saw that the **precision** and **recall** values are pretty much the same.

  

- Most of the models are returning **almost similar accuracy** for both **seen** and **unseen data** with all the three sets of data.

  

- Hence, to make the solution a **fast computing solution** we will prefer **Random Forest** with the **corr-oversampled** data as the **best fit.**

  

- As we are getting **very little overfitting** hence, we will be skipping the **hyperparameter tuning** part.





# **7. Conclusion**
 

- We saw that the **XGBoost Classifier, Random Forest Classifier** and **CatBoost Classifier** perform well.

- We saw these models on real time scenarios and determine the **best model** among them.

- Apart from that we received a good **probability score.**
