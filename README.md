# Best Feature Selection of Breast Cancer Diagnosis using Machine Learning

## Abstract:

Breast cancer, a life-threatening disease affecting millions worldwide, poses significant challenges due to its time-consuming manual determination process, potential risks, and human errors. It is a condition where cells of the breast develop unnaturally and uncontrollably, resulting in a mass called a tumor. If lumps in the breast are not addressed, they can spread to other regions of the body, including the bones, liver, and lungs. Early diagnosis is crucial for effective treatment and improved patient outcomes. In this research paper, we will focus on employing machine learning models to achieve quick identification of breast cancer tumors as benign or malignant. The primary objective is to develop a decision-making visualization pattern using swarm plots and heat maps. To accomplish this, we will utilize the Light GBM (Gradient Boosting Machine) algorithm and compare its performance against other established machine learning models, namely Logistic Regression, Gradient Boosting Algorithm, Random Forest Algorithm, and XG Boost Algorithm.

## Introduction:

Today, Breast cancer is affecting individuals, particularly women. According to the World Health Organization (WHO). It's a leading cause of female mortality. Around a million women succumb to breast cancer annually (Simon et al.) [5] with India's fatality rate at 13.92%. The prevalence is higher in Australia, Europe and the US, while Malaysia observes later-stage presentations (Abhinav Chauhan et al) [7]. Regular screening is vital due to asymptomatic cases. Early detection aids treatment and survival. Contributing factors include family history, obesity, radiation exposure, and genetics. Recently discovered, breast cancer is categorized as malignant or benign. Analyzing tumor characteristics helps differentiate them. Benign tumors are low-risk, while malignant ones spread to neighboring tissues and the body. Artificial Intelligence (AI) is being employed to classify breast cancer. AI algorithms train on datasets to label tumors as 1 for benign or 0 for malignant (Bardou, Zhang, and Ahmad et al.) [2].

The initial aim of this study is to examine breast cancer data derived from a diagnostic dataset comprising 30 feature columns and approximately 570 rows. The primary goal is to identify common characteristics in these groups that distinguish benign cases from malignant ones effectively. Subsequently, we plan to generate a heatmap visualization to identify and eliminate redundant features from the dataset. Finally, our ultimate objective is to create a machine learning model that enables users to classify breast cancer cases as either benign or malignant accurately. By accomplishing these objectives, we hope to enhance the diagnostic process and contribute to more efficient and precise breast cancer classification.

Our project aims to address challenges and propose solutions to enhance accuracy in breast cancer classification. Accuracy is a critical factor, as an imprecise model can lead to suboptimal outcomes. The research primarily centers around improving the accuracy of various algorithms, namely Logistic Regression, Gradient Boosting Algorithm, Random Forest Algorithm (Octaviani and Z Rustam et al.) [4], XG Boost Algorithm, and Light GBM Algorithm. The objective is to achieve the highest possible accuracy for the model by fine-tuning and optimizing these algorithms. By tackling accuracy-related issues, we aspire to provide more reliable and effective breast cancer classification results.

## Basic Description of the project:

Currently, India reports approximately 178,000 cases of breast cancer. However, manually determining cancer in these cases is an arduous and time-consuming process, often leading to delays and the possibility of human errors. To address this issue, we aim to develop a predictive model that can efficiently classify breast tumors as either malignant or benign using Machine Learning techniques. Our approach involves analyzing the correlation between various features, eliminating redundant data, and ultimately creating a highly accurate model. By leveraging these advanced technologies, we strive to enhance the early detection and diagnosis of breast cancer, which can significantly improve patient outcomes.

## Proposed Model:

Light Gradient Boosting (Light GBM Approach).

**Experimental Setup:**

The research methodology aims to discern the disparities between benign and malignant breast cancer cases. Initially, breast cancer data is gathered from a diagnostic dataset. The dataset is then preprocessed, and any missing values are handled by removal. Next, we utilize swarm plots to visualize and compare the features, assessing if there are distinct patterns between benign and malignant cases. Outliers in the features are identified and removed to ensure data integrity. Following the outlier removal, the preprocessed data is split into training and testing datasets. This methodology allows us to gain valuable insights into the characteristics that differentiate these types of cancer and create a robust predictive tool to aid in accurate diagnosis.

For this research, we utilized a diagnostic dataset ( The dataset has been collected from Kaggle repository) containing 569 rows and 33 columns. These 33 parameters were chosen as the basis for our analysis. These attributes play a vital role in producing visualization patterns, making it easier to generate heat maps for feature visualization.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.006.jpeg) ![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.007.png)

Once the dataset (from Kaggle’s repository) is imported using the Panda’s library, it becomes crucial to check for the presence of any missing values. The data cleaning process involves eliminating entire rows that contain any missing values. This step ensures that subsequent tasks, such as visualization, can be carried out effectively with high accuracy. Heat maps are then employed to identify and remove outliers.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.008.jpeg)

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.009.png)

Steps of execution of the above source code

1. The required libraries such as NumPy, Pandas, Matplotlib, and Seaborn are imported. These libraries provide tools for data manipulation, visualization, and analysis.
1. The breast cancer dataset is loaded from a CSV file named 'data.csv' using the Pandas `read\_csv` function.
1. The `head()` and `tail()` functions are used to display the first and last few rows of the dataset, respectively.
1. `size` and `shape` functions are used to get the total number of elements and the shape (number of rows and columns) of the dataset.
1. The column names are extracted using `data.columns` and printed.
1. `dtypes` is used to display the data types of each column in the dataset.
1. The target variable 'y' is defined as the 'diagnosis' column, which contains the labels 'M' (Malignant) or 'B' (Benign).
1. The features 'x' are defined by dropping unnecessary columns ('Unnamed: 32', 'id', 'diagnosis') from the dataset.
1. The count of each class in the target variable is visualized using a Seaborn countplot. This helps to understand the distribution of malignant (M) and benign (B) cases.
1. The counts of benign and malignant cases are printed.
1. A correlation map (heatmap) is plotted using Seaborn to visualize the correlation between different features in the dataset. This helps in understanding the relationships between variables.
1. A list of features (`drop\_list1`) is defined, and a subset of features (`x\_1`) is created by dropping the specified features from the original dataset.
1. Another correlation heatmap is plotted for the subset of features to observe the correlation pattern.

   Overall, this source code provides an initial exploration and preprocessing of the breast cancer dataset, including loading the data, defining target and features, visualizing class labels, and conducting correlation analysis. The code suggests a focus on specific features and their correlations in the dataset, possibly for feature selection in preparation for machine learning modeling.

5. **Simulation Results:**
1. 
2. **Experimental Results:**

Feature selection was applied to the initial dataset, which originally comprised 33 features. Following the feature selection process and data cleaning, the refined dataset has been reduced to 16 features.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.010.jpeg) ![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.011.png)

## Discussion:

In the preprocessing stage of our dataset in Google Colab, we first imported the dataset, which was sourced from Kaggle, using the powerful Pandas library. The dataset initially consisted of 569 rows and 33 columns, reflecting a comprehensive collection of features. However, to streamline our analysis and enhance model efficiency, a careful feature selection process was undertaken, resulting in the retention of 16 key features. This meticulous curation aimed to eliminate redundant or irrelevant variables, ensuring that the dataset remains focused on the most impactful attributes for our analysis.

Subsequently, attention was given to handling any missing or inconsistent data points. Google Colab's versatile environment facilitated the use of Pandas functions and other tools to identify and address any missing values within the selected features. Imputation techniques or removal strategies were applied judiciously to maintain the integrity of the dataset.

Normalization or scaling of numerical features was another crucial step in the preprocessing pipeline. This process ensures that all numerical variables are on a comparable scale, preventing any single feature from dominating the model training process. Standard techniques such as Min-Max scaling or Z-score normalization were employed to achieve this standardization.

Categorical variables, if present, were appropriately encoded to numeric representations using techniques like one-hot encoding, enabling seamless integration into machine learning models. This step is pivotal for algorithms that rely on numerical inputs, ensuring that all features contribute meaningfully to the model's learning process.

In conclusion, the preprocessing of our Kaggle-sourced dataset in Google Colab involved meticulous steps such as feature selection, handling missing values, normalization of numerical features, and encoding categorical variables. These steps collectively contribute to the creation of a refined, clean, and well-structured dataset, laying the foundation for robust and accurate machine learning models in subsequent stages of our analysis.

## Future Work:

We are yet to train and test the algorithm with the refined datasets and build the model to achieve the highest possible accuracy.

## Conclusion

After removing the outliers, we found that 16 features remained, which will significantly contribute to the overall accuracy of the model. We would now train the algorithm through this refined dataset and achieve the highest possible accuracy.

Hopefully, this accuracy of detection of Breast Cancer will aid individuals in receiving early cancer treatment and proactively manage their lives.
