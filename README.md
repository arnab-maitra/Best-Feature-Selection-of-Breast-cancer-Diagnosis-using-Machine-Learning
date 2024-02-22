# Best-Feature-Selection-of-Breast-cancer-Diagnosis-using-Machine-Learning

**BEST FEATURE SELECTION OF BREAST CANCER DIAGNOSIS USING MACHINE LEARNING**

A MINOR PROJECT REPORT SUBMITTED IN PARTIAL FULFILLMENT OF THE REQUIREMENT FOR THE DEGREE OF

**BACHELOR OF TECHNOLOGY**

IN

**COMPUTER SCIENCE AND ENGINEERING** SUBMITTED BY

**Name Univ. Roll No.** Arnab Maitra 10800120178 Subhadeep Puitandi 10800120167 Ankita Mukherjee 10800120174 Arijita Roy 10800120063

UNDER THE GUIDANCE OF

**MRS. VEDATRAYEE CHATTERJEE**

Assistant Professor

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.001.png)

DEPARTMENT OF COMPUTER SCIENCE AND ENGINEERING **ASANSOL ENGINEERING COLLEGE**

AFFILIATED TO

MAULANA ABUL KALAM AZAD UNIVERSITY OF TECHNOLOGY November, 2023

***Contents***

Certificate of Recommendation……………………………………………………………… iii Certificate of Approval………………………………………………………………............. iv Acknowledgement…………………………………………………………............................ v Abstract…………………………………………………………………………...………….. vi List of Figures………………………………………………………………………………. vii

1. **Preface………………………………………………………………………………**
1. Introduction……………………………………………………...…………… 1
1. Motivation of the project………………………………….………………….. 1
1. Basic description of the project………………………….…………………… 1
2. **Literature Review…………..………………………………………………………**
1. General……………………………………………………...………………… 2
1. Review of related works …………………………. …………......….…...…… 2
3. **Related Theories and Algorithms…………..……………………………………..**
1. Fundamental theories underlying the work.………………………………….. 4
1. Fundamental algorithms………………………………….…………………… 6
4. **Proposed model/algorithm…………………………………….………………….**
1. Proposed model……………………………………………………………….. 11
1. Proposed algorithms……………………….…………………………………. 12
5. **Simulation Results…………………………………………...…………………….…**
1. Experimental set up ……………………………………………..………….. 14
1. Experimental results………...……………...……… 16
6. **Discussion and Conclusion ……...…………………………………………….…….**
1. Discussion…………………………………..………………………….…….. 17
1. Future work…………………………………..….……………………...…….. 17
1. Conclusion…………………………………………………………………….. 18

**References…………………………………………………………………………….**

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.002.png)

***Certificate of Recommendation***

I hereby recommend that the Minor Project Report entitled, **“Best Feature Selection of Breast Cancer Diagnosis using Machine Learning”** carried out under my supervision by the group of students listed below may be accepted in partial fulfilment of the requirement for the degree of “Bachelor of Technology in Computer Science and Engineering” of Asansol Engineering College under MAULANA ABUL KALAM AZAD UNIVERSITY OF TECHNOLOGY.

**Name Univ. Roll No.** Arnab Maitra 10800120178 Subhadeep Puitandi 10800120167 Ankita Mukherjee 10800120174 Arijita Roy 10800120063

……..…..………………

Mrs. Vedatrayee Chatterjee

Project Supervisor

Dept. of Comp. Sc. & Engineering, Asansol Engineering College,    Asansol-713305

Countersigned: ……..…..……………… (Dr. Monish Chatterjee)

Head of the Department Dept. of Comp. Sc. & Engg

Asansol Engineering College, Asansol-713305

iii

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.003.png)

***Certificate of Approval***

The Minor Project Report is hereby approved as a creditable study of an engineering subject carried out and presented in a manner satisfactory to warrant its acceptance for the degree for which it has been submitted. It is understood that by this approval the undersigned does not necessarily endorse or approve any statement made, opinion expressed or conclusion drawn therein but approve the report only for the purpose for which it is submitted.

…………………………………

(**Mrs. Vedatrayee Chatterjee**)

Project Supervisor.

Dept. of Comp. Sc. & Engg. Asansol Engineering College, Asansol-713305

iv

***Acknowledgement***

It is our great privilege to express our profound and sincere gratitude to our Project Supervisor, **Mrs. Vedatrayee Chatterjee** for providing us a very cooperative and precious guidance at every stage of the present project work being carried out under his/her supervision. His valuable advice and instructions in carrying out the present study has been a very rewarding and pleasurable experience that has greatly benefited us throughout the course of work.

We would like to convey our sincere gratitude towards Dr. Monish Chatterjee, Head of the Department of Computer Science and Engineering of Asansol Engineering College for providing us the requisite support for timely completion of our work. We would also like to pay our heartiest thanks and gratitude to all the teachers of the Department of Computer Science and Engineering, for various suggestions being provided in attaining success in our work.

We would like to express our earnest thanks to Mr. Suman Mallick, of CSE Project Lab for his technical assistance provided during our project work.

Finally, I would like to express my deep sense of gratitude to my parents for their constant motivation and support throughout my work.

………………………………… ARNAB MAITRA

………………………………… SUBHADEEP PUITANDI

………………………………… ANKITA MUKHERJEE

………………………………… ARIJITA ROY

v

***Abstract***

Breast cancer, a life-threatening disease affecting millions worldwide, poses significant challenges due to its time-consuming manual determination process, potential risks, and human errors. It is a condition where cells of the breast develop unnaturally and uncontrollably, resulting in a mass called a tumor. If lumps in the breast are not addressed, they can spread to other regions of the body, including the bones, liver, and lungs. Early diagnosis is crucial for effective treatment and improved patient outcomes. In this research paper, we focus on employing machine learning models to achieve quick identification of breast cancer tumors as benign or malignant. The primary objective is to develop a decision-making visualization pattern using swarm plots and heat maps. To accomplish this, we will utilize the Light GBM (Gradient Boosting Machine) algorithm and compared its performance against other established machine learning models, namely Logistic Regression, Gradient Boosting Algorithm, Random Forest Algorithm, and XG Boost Algorithm.

vi

***List of Figures***

Fig. 4.1.1 Flowchart of Light GBM Algorithm Page no 12 Fig. 5.1.2 Original Dataset collected from Kaggle repository Page no 15 Fig. 5.1.3 Swarm Plot Graphs were plotted Page no 16 Fig. 5.2.4 Refined Dataset after Removal of Outliers Page no 16

vii

1. **Preface**
1. **Introduction:**

Today, Breast cancer is affecting individuals, particularly women. According to the World Health Organization (WHO). It's a leading cause of female mortality. Around a million women succumb to breast cancer annually (Simon et al.) [5] with India's fatality rate at 13.92%. The prevalence is higher in Australia, Europe and the US, while Malaysia observes later-stage presentations (Abhinav Chauhan et al) [7]. Regular screening is vital due to asymptomatic cases. Early detection aids treatment and survival. Contributing factors include family history, obesity, radiation exposure, and genetics. Recently discovered, breast cancer is categorized as malignant or benign. Analyzing tumor characteristics helps differentiate them. Benign tumors are low-risk, while malignant ones spread to neighboring tissues and the body. Artificial Intelligence (AI) is being employed to classify breast cancer. AI algorithms train on datasets to label tumors as 1 for benign or 0 for malignant (Bardou, Zhang, and Ahmad et al.) [2].

2. **Motivation of the project:**

The initial aim of this study is to examine breast cancer data derived from a diagnostic dataset comprising 30 feature columns and approximately 570 rows. The primary goal is to identify common characteristics in these groups that distinguish benign cases from malignant ones effectively. Subsequently, we plan to generate a heatmap visualization to identify and eliminate redundant features from the dataset. Finally, our ultimate objective is to create a machine learning model that enables users to classify breast cancer cases as either benign or malignant accurately. By accomplishing these objectives, we hope to enhance the diagnostic process and contribute to more efficient and precise breast cancer classification.

Our project aims to address challenges and propose solutions to enhance accuracy in breast cancer classification. Accuracy is a critical factor, as an imprecise model can lead to suboptimal outcomes. The research primarily centers around improving the accuracy of various algorithms, namely Logistic Regression, Gradient Boosting Algorithm, Random Forest Algorithm (Octaviani and Z Rustam et al.) [4], XG Boost Algorithm, and Light GBM Algorithm. The objective is to achieve the highest possible accuracy for the model by fine-tuning and optimizing these algorithms. By tackling accuracy-related issues, we aspire to provide more reliable and effective breast cancer classification results.

3. **Basic Description of the project:**

Currently, India reports approximately 178,000 cases of breast cancer. However, manually determining cancer in these cases is an arduous and time-consuming process, often leading to delays and the possibility of human errors. To address this issue, we aim to develop a predictive model that can efficiently classify breast tumors as either malignant or benign using Machine Learning techniques. Our approach involves analyzing the correlation between various features, eliminating redundant data, and ultimately creating a highly accurate model. By leveraging these advanced technologies, we strive to enhance the early detection and diagnosis of breast cancer, which can significantly improve patient outcomes.

2. **Literature Review:**
1. **General**

Breast cancer remains a significant global health concern, and the integration of machine learning (ML) techniques has become pivotal in enhancing predictive models and diagnostic accuracy. This literature review synthesizes findings from various studies that employ ML algorithms for breast cancer prediction and diagnosis.

In conclusion, the reviewed literature highlights the diverse applications of machine learning in breast cancer prediction and diagnosis. From survival prediction to histology image classification and feature selection, researchers continue to explore innovative approaches to enhance the accuracy and efficiency of breast cancer diagnostic models. The integration of advanced ML techniques not only contributes to improved predictive models but also paves the way for personalized and effective breast cancer management strategies.

2. **Review of Related Works**

Afshar et al. [1] address the critical aspect of predicting breast cancer survival. Their work involves the application of multiple imputation techniques, showcasing the importance of handling missing data in survival prediction models. The study emphasizes the significance of accurate survival predictions, providing insights that can inform treatment strategies and improve patient outcomes.

Histological image analysis is a powerful tool for breast cancer diagnosis. Bardou et al. [2] leverage Convolutional Neural Networks (CNNs) to classify breast cancer based on histology images. The study highlights the potential of deep learning in image-based classification, demonstrating the efficacy of CNNs in capturing intricate patterns that contribute to accurate diagnosis.

Derangula et al. [3] focus on the importance of feature selection in breast cancer data. They employ Gradient Boosting, emphasizing the role of relevant features in improving model performance. Feature selection is crucial for enhancing the interpretability of models and mitigating overfitting, and this study contributes insights into the application of Gradient Boosting for this purpose.

Octaviani and Rustam [4] explore the use of Random Forests for breast cancer prediction. Their study showcases the effectiveness of ensemble methods in handling diverse data types. Random Forests, by aggregating decision trees, demonstrate robustness in handling high-dimensional data, emphasizing their suitability for breast cancer prediction.

Simon et al. [5] delve into the intersection of cardiometabolic risk factors and breast cancer survival. This study broadens the perspective by considering additional factors beyond traditional predictors. Understanding the broader health context is crucial for a comprehensive approach to breast cancer prediction and personalized treatment planning.

Sultana and Jilani [6] focus on breast cancer prediction using Logistic Regression and multi-class classifiers. Logistic Regression, a classic ML algorithm, is employed alongside other classifiers. This study contributes to the understanding of the comparative performance of various algorithms in breast cancer prediction, considering both simplicity and accuracy.

Vyas et al. [7] provide a comprehensive overview of various ML techniques for breast cancer detection. The study emphasizes the diversity of methods available for addressing this complex problem. The review encompasses a range of algorithms, contributing to the broader understanding of their applicability in breast cancer detection.

Joshi and Mehta [8] conduct a comparative analysis of various ML techniques for breast cancer diagnosis. The study sheds light on the strengths and weaknesses of different algorithms, aiding researchers and practitioners in selecting appropriate models for specific diagnostic scenarios.

Nahid and Kong [9] present a survey on the involvement of ML in breast cancer image classification. The study provides an overview of the evolving landscape of image-based diagnostic approaches, highlighting the role of ML in enhancing accuracy and efficiency in breast cancer diagnosis from imaging data.

Asri et al. [10] contribute insights into the use of ML algorithms for breast cancer risk prediction and diagnosis. The study emphasizes the potential of ML in integrating various data sources and features for more comprehensive risk assessment and accurate diagnosis.

Bazazeh and Shubair [11] undertake a comparative study of ML algorithms for breast cancer detection and diagnosis. This research provides valuable insights into the performance of different algorithms, aiding in the selection of suitable models for specific diagnostic tasks.

Hassan et al. [12] conduct a comparative assessment of ML algorithms with the LASSO technique for breast cancer detection and prediction. The study explores the effectiveness of LASSO in feature selection and its impact on the performance of various ML models.

3. **Related Theories and Algorithms**
1. **Fundamental theories underlying the work**

Feature selection is a crucial step in machine learning, especially for tasks like breast cancer prediction. The goal is to choose a subset of relevant features that can effectively represent the underlying patterns in the data.

- Relevance and Redundancy:

Relevance: The selected features should be highly correlated with the target variable (benign or malignant). Features that have a strong relationship with the outcome are more likely to contribute to the predictive power of the model.

Redundancy: It's important to avoid selecting features that provide similar information. Redundant features do not add much value and may even introduce noise into the model. Techniques like correlation analysis can help identify and remove redundant features.

- Filter, Wrapper, and Embedded Methods:

Filter Methods: The filter method is a prominent approach for feature selection. Filter methods determine feature relevance by employing statistical metrics prior to model training. This process streamlines feature selection, enhancing the efficiency of the machine learning pipeline. It involves steps like computing scores for each feature based on metrics capturing their relationship with the target variable, ranking features according to these scores, and setting a threshold to retain or discard features. Notably, filter methods assess feature relevance independently, making them computationally efficient and suitable for large datasets. These methods are model-agnostic, allowing their application across diverse problems and data types. Common scoring metrics include correlation coefficients, mutual information, and variance thresholding. (Hiba Asri, Hajar Mousannif ,Hassan Al Moatassime, Thomas Noel et al.) [10]. Common filter methods include chi-squared test, information gain, and correlation analysis.

Wrapper Methods: The wrapper method stands as an advanced and dynamic technique for feature selection within the realm of machine learning. Unlike filter methods that employ statistical measures, the wrapper method takes a more comprehensive approach by iteratively training and evaluating machine learning models using various feature subsets. This technique involves generating subsets, training models, and evaluating performance for each subset, guided by a chosen performance metric. The subset yielding the best model performance is then selected. Unlike filter methods, the wrapper method considers feature interactions, enabling it to capture complex relationships in the data. Its model-centric approach aligns with the ultimate goal of achieving superior predictive accuracy. However, it does come with computational costs due to its repeated model training and evaluation, and careful handling is required to avoid overfitting. The wrapper method's ability to fine-tune feature selection for optimal model performance makes it a valuable asset in situations where precision is paramount. (Hiba Asri, Hajar Mousannif ,Hassan Al Moatassime, Thomas Noel et al.) [10]. Examples include recursive feature elimination (RFE) and forward/backward feature selection.

Embedded Methods: The embedded method represents a dynamic and sophisticated approach to feature selection in the realm of machine learning. Unlike filter methods that analyze features prior to model training or wrapper methods that evaluate features independently, the embedded method seamlessly integrates feature selection within the model building process. This method takes advantage of algorithms that inherently assess feature importance while learning from the data. As the model iteratively refines its parameters, it simultaneously adjusts the relevance of features, automatically assigning higher importance to those that significantly contribute to its performance. Algorithms like Lasso Regression, Decision Trees, Random Forests, Gradient Boosting, and certain Neural Networks exemplify embedded methods by either penalizing irrelevant features or calculating feature importance scores. This approach leads to efficient feature selection, insights into feature impact, and often prevents overfitting by penalizing unnecessary attributes. However, it's crucial to note that the applicability of embedded methods is tied to the specific algorithm chosen and its inherent feature selection capabilities. In essence, embedded methods strike a balance between filter methods' efficiency and wrapper methods' performance optimization, yielding both accurate and interpretable models. (Arpita Joshi and Dr. Ashish Mehta et al.) [8].

- Recursive Feature Elimination:

RFE, or Recursive Feature Elimination, operates as a wrapper-style feature selection technique that incorporates a distinct machine learning algorithm at its core. Unlike filter-based methods that score individual features, RFE iteratively refines the feature set. It commences with all features from the training dataset and progressively prunes them until the desired count is achieved. This iterative procedure involves leveraging the designated machine learning algorithm to assess feature importance, discarding the least relevant features, and subsequently retraining the model. The RFE process continues iteratively, with features being removed step by step, until the specified target number of features remains in the selected subset. This interplay between the wrapper-style approach and the internal utilization of filter-based feature ranking enables RFE to effectively identify a subset of features that optimally contribute to the model's performance. (Arpita Joshi and Dr. Ashish Mehta et al.) [8], (Abdullah-Al Nahid and Yinan Kong et al.) [9].

- Cross-Validation:

Cross-validation is essential for assessing the generalization performance of the selected feature subset. It helps in estimating how well the model will perform on unseen data. Techniques like k-fold cross-validation ensure that the evaluation is robust and not dependent on a particular training-test split.

- Domain Knowledge:

Incorporating domain knowledge is crucial, especially in medical applications like breast cancer prediction. Understanding the biological significance of features can guide the selection process. Collaboration between machine learning experts and domain experts is often beneficial.

- Dimensionality Reduction:

Feature selection is closely related to dimensionality reduction. Principal Component Analysis (PCA) and other dimensionality reduction techniques can be employed to transform the feature space and identify the most informative dimensions.

- Stability and Consistency:

A good feature selection method should be stable, meaning that it produces consistent results across different subsets of the data. Stability ensures that the selected features are not heavily influenced by random variations in the dataset.

- Scalability:

The method should be scalable to handle datasets with a large number of features. Some feature selection techniques may become computationally expensive as the dimensionality of the data increases.

- Model Interpretability:

Depending on the context, the interpretability of the model may be crucial. Some feature selection methods result in a subset of features that are easier to interpret, which is important in medical applications where understanding the decision-making process is essential.

2. **Fundamental algorithms**
- Support Vector Machine (SVM):

The primary goal of the support vector machine (SVM) algorithm is to identify a hyperplane within an N-dimensional space, where N represents the number of features, that effectively segregates data points into distinct classes. Given a set of data points with different classes, numerous potential hyperplanes can be considered to separate them. The key objective is to identify a hyperplane that exhibits the maximum margin, indicating the greatest distance between data points of the two classes.

Hyperplanes function as decision boundaries that aid in classifying data points. By categorizing data points on either side of the hyperplane, distinct classes can be assigned. Furthermore, the dimensionality of the hyperplane corresponds to the number of features present. Support vectors denote data points positioned in close proximity to the hyperplane, significantly influencing its position and orientation. Leveraging these support vectors, the algorithm strives to maximize the margin of separation between the two classes. Notably, altering or removing support vectors would lead to a shift in the hyperplane's position. SVM stands out as a powerful classifier, particularly when there exists a well-defined separation margin and the data features are high-dimensional. However, its suitability diminishes when handling large datasets due to the extended training time required. Additionally, SVM's performance deteriorates in scenarios where the dataset is tainted with significant levels of noise. (Arpita Joshi and Dr. Ashish Mehta et al.) [8].

- K-Nearest Neighbour (KNN):

K-Nearest Neighbour (KNN) stands out as one of the elementary Machine Learning algorithms, grounded in the principles of Supervised Learning. The KNN algorithm operates on the premise of likening the new, incoming data to the pre-existing instances and then assigning the new data point to the category most akin to the established categories. In essence, KNN taps into the reservoir of stored data and uses similarity to guide its classification process. This method works particularly well when the data is structured and categorically organised. The operational logic of KNN revolves around identifying data points within the dataset that closely align with the new data point under consideration. The algorithm evaluates the distances between these points, sorting them based on proximity to the target point. The measurement of distance is typically conducted using various methodologies, with the Euclidean distance being a widely favoured choice among experts. The subsequent step involves selecting a specific count of neighbouring points whose distances are minimal in relation to other points. These chosen points, often referred to as "neighbours," play a pivotal role in the classification process. Notably, the selection of these neighbours is typically based on an odd number, which aligns with the number of classes present in the problem. For instance, in a binary classification task, the highest count of points from one class will be taken as the basis for classification. KNN is admired for its simplicity in implementation and its ability to manage substantial datasets. However, it comes with a trade-off: the computational cost can be high due to the need to calculate distances across the entire training set. Additionally, the choice of the parameter 'K' – the number of neighbours to consider – can influence the algorithm's complexity and, subsequently, its performance. (Arpita Joshi and Dr. Ashish Mehta et al.) [8].

- Random Forest

Random Forest is a type of supervised learning algorithm that operates by amalgamating multiple Decision Trees. A Decision Tree is structured hierarchically, with nodes representing specific conditions based on a set of features. The branches within the tree steer the decision-making process towards the leaf nodes, which ultimately determine the class labels of the data instances. Decision Trees can be generated using either Recursive Partitioning or Conditional Inference Tree methods. Recursive Partitioning involves constructing a Decision Tree incrementally by deliberating whether to split each node further. This process entails partitioning the source dataset into subsets through attribute value tests. The recursion continues until a node's subset contains only instances with identical target variable values. In contrast, the Conditional Inference Tree approach is grounded in statistical principles. It employs non-parametric tests as criteria for splitting nodes, with corrections for multiple testing to mitigate the risk of overfitting. Random Forest is particularly well-suited for modeling high-dimensional data due to its capacity to handle diverse data types such as missing values, continuous variables, as well as categorical and binary data. However, it's worth noting that when working with very large datasets, the memory usage can increase due to the size of the trees generated. One common challenge is the potential for overfitting, which emphasizes the need to fine-tune the algorithm's hyper parameters to achieve optimal performance. (Arpita Joshi and Dr. Ashish Mehta et al.) [8], (Hiba Asri, Hajar Mousannif, Hassan Al Moatassime, Thomas Noel et al.) [10].

- Logistic Regression

In the realm of linear regression, the derived hyperplane is insufficient for predicting the dependent variable through the independent variables. This limitation becomes pronounced, especially when grappling with categorical data. This is where logistic regression steps in. Logistic regression shines when categorical data is in play, diverging from linear regression's approach of predicting continuous outcomes. Instead, logistic regression tackles the task of discerning the truth or falsehood of an assertion, effectively delving into classification problems. Unlike its linear counterpart, logistic regression leverages the sigmoid function to transform the independent variable into a probability expression bounded within the range of 0 to 1 concerning the dependent variable. This probabilistic nature equips logistic regression to not only offer probabilities but also to adeptly categorize new samples based on a combination of continuous and discrete measurements. This versatility renders logistic regression a sought-after algorithm in the realm of Machine Learning. However, it's worth noting that logistic regression does carry a limitation in the form of its assumption regarding the linearity between the dependent and independent variables. This assumption can pose challenges when dealing with datasets that don't conform to linear relationships, potentially affecting the algorithm's predictive accuracy. (Arpita Joshi and Dr. Ashish Mehta et al.) [8].

- Decision Trees

Decision Trees (DT) serve a dual purpose, finding utility in both classification and regression tasks. This versatile algorithm employs a tree structure characterized by two fundamental node types: the decision node and the leaf node. The decision node embodies a test that guides the traversal of the tree, while the ultimate classification or prediction occurs within the leaf node. In essence, Decision Trees excel at capturing intricate decision-making processes in a highly interpretable format. This makes them valuable tools not only for classifying data points but also for predicting continuous outcomes through regression. By effectively compartmentalizing decisions into decision nodes and outcomes into leaf nodes, Decision Trees offer an intuitive approach to solving a wide array of predictive tasks. (Sarthak Vyas, Abhinav Chauhan, Deepak Rana, Noman Ansari et al.) [7].

- Ensemble Methods

Ensemble learning stands as a potent Machine Learning technique where multiple distinct models are trained to collectively address a shared problem, ultimately yielding enhanced outcomes. The core principle underlying ensemble learning is the belief that by effectively amalgamating weak models, we can achieve heightened accuracy and robustness in our predictions. The underlying concept is grounded in the notion that the amalgamation of individual models can lead to a final model that not only outperforms the individual constituents but also demonstrates a greater capacity to withstand variations and uncertainties in the data. This collaborative approach capitalizes on the strengths of each individual model, creating a formidable ensemble that contributes to more accurate and reliable predictions. (Sarthak Vyas, Abhinav Chauhan, Deepak Rana, Noman Ansari et al.) [7], (Simon, Michael S, et al.) [5].

- Bagging

During the process of model preparation, whether dealing with a classification or regression task, we construct a function that takes input data and produces an output result. This function is devised based on the characteristics of the training dataset. It's imperative to acknowledge that due to the inherent variability present within the training dataset (reflecting observed instances drawn from an underlying, unknown distribution), the resultant fitted model is also subject to this variability. If an entirely different dataset had been observed, the model generated would indeed diverge, showcasing a distinct configuration and behavior. (Sarthak Vyas, Abhinav Chauhan, Deepak Rana, Noman Ansari et al.) [7].

- Naïve Bayes

The Naïve Bayes classifier stands as a prominent supervised learning algorithm designed for classification tasks. Its foundation rests upon the Bayes theorem, a probabilistic formula that determines the probability of an event occurring given that another event has already taken place. As a versatile tool, Naïve Bayes finds extensive use across industries due to its simplicity and efficacy in various Machine Learning applications. Naïve Bayes operates on the assumption of feature independence, a premise that, while simplifying computations, often deviates from the intricate interdependencies present in real-world scenarios. This oversimplification can restrict the algorithm's practicality across complex use cases. An inherent challenge faced by this algorithm is the 'zero-frequency problem,' wherein it assigns zero probability to a categorical variable category that wasn't encountered during training. This limitation can be addressed by employing smoothing techniques that introduce minimal probabilities to unseen categories, enhancing the algorithm's robustness. Another noteworthy limitation of Naïve Bayes is its reliance on sizable datasets to achieve peak accuracy. The algorithm's performance tends to flourish with an ample volume of data, allowing it to draw more reliable conclusions and make accurate predictions. In summation, while Naïve Bayes offers a straightforward and potent approach to classification, its success hinges on acknowledging its assumptions and understanding its limitations. By addressing challenges such as the 'zero-frequency problem' and considering its applicability to specific data scenarios, practitioners can harness its capabilities effectively. (Abdullah-Al Nahid and Yinan Kong et al.) [9].

- Boosting

Boosting strategies operate with a similar underlying principle as ensemble techniques: they assemble an ensemble of models, aimed at collectively achieving the performance of a strong, superior learner. However, in contrast to the focus of ensembling on variance reduction, boosting adopts a distinct approach. It dynamically binds multiple weak learners together in an adaptive fashion, where each individual model in the ensemble receives more attention in areas where previous models were lacking efficacy. Each newly introduced model concentrates its efforts on challenging instances, progressively refining the overall ensemble's performance. This iterative process culminates in the creation of a robust learner with reduced bias, even though boosting can also incidentally contribute to variance reduction. Boosting is not only applicable to classification but also extends to regression tasks. While primarily geared towards mitigating bias, boosting favors base models that possess low variance and high bias. Adaboost and Gradient Boosting stand as two significant algorithms within the realm of boosting. These methodologies diverge in their approach to creating and combining the weak learners throughout the iterative process. (Hiba Asri, Hajar Mousannif ,Hassan Al Moatassime, Thomas Noel et al.) [10].

- Adaptive / Adaboost Boosting

Adaptive boosting (Adaboost) updates the weights attached to each training data point, whereas Gradient Boosting modifies the values of these points. This fundamental distinction arises from their respective approaches to addressing the optimization problem of approximating a composite model with weighted combinations of weak learners. (Sarthak Vyas, Abhinav Chauhan, Deepak Rana, Noman Ansari et al.) [7], (Hiba Asri, Hajar Mousannif, Hassan Al Moatassime, Thomas Noel et al.) [10], (Derangula, Anusha, et al.) [3].

- Gradient Boosting

Gradient boosting represents a state-of-the-art predictive approach that iteratively tackles a complex optimization challenge, yielding a model expressed as a linear combination of fundamental predictors—typically in the form of decision trees. This innovative methodology orchestrates the assembly of a predictive model and subsequently refines its generality by facilitating optimization for a wide range of differentiable loss functions. Employing a gradient descent algorithm, this technique systematically reduces the loss by introducing new decision trees. Notably, gradient boosting proves its efficacy in resolving predictive modeling intricacies across both regression and classification tasks. The foundation of Gradient Boosting (GB) lies in the notion that the most promising subsequent model, when integrated with existing models, serves to minimize overall predictive errors. This approach leverages the insight that integrating prior model outcomes into the construction of new models contributes to error reduction. For instance, the GB framework accommodates optimization across diverse loss functions and offers a spectrum of hyperparameter adjustments, endowing the fitting process with a high degree of adaptability and flexibility. (Dana Bazazeh and Raed Shubair et al.) [11], (Md. Mehedi Hassan, Md. Mahedi Hassan, Farhana Yasmin, Md. Asif Rakib Khan, Sadika Zaman, Galibuzzaman, Khan Kamrul Islam, Anupam Kumar Bairagi et al.) [12].

❖ Extreme Gradient Boosting (XGBoost / XGB)

XGBoost (XGB) stands as a gradient boosting framework rooted in ensemble machine learning strategies that leverage decision trees. This technique's swiftness in processing and capacity for scalability suggest its potential in yielding highly valuable insights. XGB finds utility across both regression and classification tasks. At its core, this methodology aims to achieve precise classification by progressively identifying weak algorithms. It employs the gradient descent technique to craft individualized decision trees, initially establishing sets of threshold values that undergo iterative refinement via the minimization of residuals during tree construction. Within the context of gradient boosting, weak learners manifest as regression trees, with each tree mapping an input dataset to specific leaves bearing continuous markers. The process entails minimizing a regularized function (encompassing L1 and L2 norms), characterized by a convex loss function rooted in the disparity between predictions and target outputs. The training process incrementally introduces new trees to predict the residuals or errors of preceding trees. These predictions are then amalgamated with the outputs of prior trees to ultimately generate the final prediction. (Dana Bazazeh and Raed Shubair et al.) [11], (Md. Mehedi Hassan, Md. Mahedi Hassan, Farhana Yasmin, Md. Asif Rakib Khan, Sadika Zaman, Galibuzzaman, Khan Kamrul Islam, Anupam Kumar Bairagi et al.) [12].

4. **Proposed Model / Algorithm:**
1. **Proposed Model**

The approach proposed is Light Gradient Boosting (Light GBM Approach).

A novel approach in breast cancer detection has been introduced utilizing the Light Gradient Boost machine learning technique. This innovative method aims to transform initially weak learners into robust ones, thereby achieving enhanced accuracy in breast cancer detection. Unlike the conventional employment of weak learners as standalone classifiers, this technique leverages a boosting ensemble to achieve heightened classification accuracy. In this approach, the weak learners are harnessed as classifiers, which alone may not yield optimal classification accuracy. However, the concept of a strong learner emerges through the ensemble of these weak classifiers. This ensemble-based boosting technique is rooted in tree-based classification.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.004.jpeg)

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.005.png)

Notably, the Light Gradient Boost machine learning technique molds the decision tree classifier into a unique weak learner structure, characterized by a vertical orientation. This innovative design, termed the "Leaf-wise Decision Tree Algorithm," showcases its distinctiveness in minimizing training loss compared to alternative algorithms. Through these advancements, the Light Gradient Boost technique demonstrates its potential to significantly improve breast cancer detection accuracy, thus offering promising avenues for enhanced medical diagnostics.

2. **Proposed algorithms**

Source Code

- Import required libraries

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

from matplotlib.pyplot import figure import seaborn as sns

- Load the data

data = pd.read\_csv('data.csv') data.head()

data.tail() data.size data.shape

- Get feature names col = data.columns print(col)

  data.dtypes

- Target variable

y = data.diagnosis # M or B

- Features

drop\_list = ['Unnamed: 32', 'id', 'diagnosis'] x = data.drop(drop\_list, axis=1)

x.head()

- Visualize the class labels

ax = sns.countplot(x=y, label="Count") # M = 212, B = 357 B, M = y.value\_counts()

print('Number of Benign:', B)

print('Number of Malignant:', M)

- Correlation map

f, ax = plt.subplots(figsize=(18, 18))

sns.heatmap(x.corr(), annot=True, linewidths=.5, fmt='.1f', ax=ax)

drop\_list1 = ['perimeter\_mean', 'radius\_mean', 'compactness\_mean', 'concave points\_mean', 'radius\_se', 'perimeter\_se', 'radius\_worst', 'perimeter\_worst', 'compactness\_worst', 'concave points\_worst', 'compactness\_se', 'concave points\_se', 'texture\_worst', 'area\_worst']

x\_1 = x.drop(drop\_list1, axis=1)

- Correlation heatmap

f, ax = plt.subplots(figsize=(14, 14))

sns.heatmap(x\_1.corr(), annot=True, linewidths=.5, fmt='.1f', ax=ax)

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
1. **Experimental Setup:**

The research methodology aims to discern the disparities between benign and malignant breast cancer cases. Initially, breast cancer data is gathered from a diagnostic dataset. The dataset is then preprocessed, and any missing values are handled by removal. Next, we utilize swarm plots to visualize and compare the features, assessing if there are distinct patterns between benign and malignant cases. Outliers in the features are identified and removed to ensure data integrity. Following the outlier removal, the preprocessed data is split into training and testing datasets. This methodology allows us to gain valuable insights into the characteristics that differentiate these types of cancer and create a robust predictive tool to aid in accurate diagnosis.

For this research, we utilized a diagnostic dataset ( The dataset has been collected from Kaggle repository) containing 569 rows and 33 columns. These 33 parameters were chosen as the basis for our analysis. These attributes play a vital role in producing visualization patterns, making it easier to generate heat maps for feature visualization.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.006.jpeg) ![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.007.png)

Once the dataset (from Kaggle’s repository) is imported using the Panda’s library, it becomes crucial to check for the presence of any missing values. The data cleaning process involves eliminating entire rows that contain any missing values. This step ensures that subsequent tasks, such as visualization, can be carried out effectively with high accuracy. Heat maps are then employed to identify and remove outliers.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.008.jpeg)

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.009.png)

2. **Experimental Results:**

Feature selection was applied to the initial dataset, which originally comprised 33 features. Following the feature selection process and data cleaning, the refined dataset has been reduced to 16 features.

![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.010.jpeg) ![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.011.png)

6. **Discussion and Conclusion:**
1. **Discussion:![](Aspose.Words.c70bfd3e-88f9-4f23-9476-2a730b1ae8a1.012.jpeg)**

In the preprocessing stage of our dataset in Google Colab, we first imported the dataset, which was sourced from Kaggle, using the powerful Pandas library. The dataset initially consisted of 569 rows and 33 columns, reflecting a comprehensive collection of features. However, to streamline our analysis and enhance model efficiency, a careful feature selection process was undertaken, resulting in the retention of 16 key features. This meticulous curation aimed to eliminate redundant or irrelevant variables, ensuring that the dataset remains focused on the most impactful attributes for our analysis.

Subsequently, attention was given to handling any missing or inconsistent data points. Google Colab's versatile environment facilitated the use of Pandas functions and other tools to identify and address any missing values within the selected features. Imputation techniques or removal strategies were applied judiciously to maintain the integrity of the dataset.

Normalization or scaling of numerical features was another crucial step in the preprocessing pipeline. This process ensures that all numerical variables are on a comparable scale, preventing any single feature from dominating the model training process. Standard techniques such as Min-Max scaling or Z-score normalization were employed to achieve this standardization.

Categorical variables, if present, were appropriately encoded to numeric representations using techniques like one-hot encoding, enabling seamless integration into machine learning models. This step is pivotal for algorithms that rely on numerical inputs, ensuring that all features contribute meaningfully to the model's learning process.

In conclusion, the preprocessing of our Kaggle-sourced dataset in Google Colab involved meticulous steps such as feature selection, handling missing values, normalization of numerical features, and encoding categorical variables. These steps collectively contribute to the creation of a refined, clean, and well-structured dataset, laying the foundation for robust and accurate machine learning models in subsequent stages of our analysis.

2. **Future Work:**

We are yet to train and test the algorithm with the refined datasets and build the model to achieve the highest possible accuracy.

3. **Conclusion**

After removing the outliers, we found that 16 features remained, which will significantly contribute to the overall accuracy of the model. We would now train the algorithm through this refined dataset and achieve the highest possible accuracy.

Hopefully, this accuracy of detection of Breast Cancer will aid individuals in receiving early cancer treatment and proactively manage their lives.

**References:**

1. Afshar, Lotfnezhad, et al. “Prediction of Breast Cancer Survival by Machine Learning Methods: An Application of Multiple Imputation”. Iran J Public Health (2021): 10.18502/ijph.v50i3.5606.
1. Bardou, Dalal, Kun Zhang, and Sayed Mohammad Ahmad et al. “Classification of Breast Cancer Based on Histology Images Using Convolutional Neural Networks”. IEEE Access 6 (2018): 24680–24693. 10.1109/ACCESS.2018.2831280.
1. Derangula, Anusha, et al. “Feature Selection of Breast Cancer Data Using Gradient Boosting” (2020): https://ejmcm.com/article\_2569\_a7c3766658c69272f70820a964a9cd36.pdf.
1. Octaviani, T L and Z Rustam et al. “Random forest for breast cancer prediction”. Proceedings of the 4th International Symposium on Current Progress in Mathematics and Sciences (2019): 10.1063/1.5132477.
1. Simon, Michael S, et al. “Cardiometabolic risk factors and survival after cancer in the Women’s Health Initiative”. Cancer 127.4 (2021): 598– 608. 10.1002/cncr.33295.
1. Sultana, Jabeen and Abdul Khader Jilani et al. “Predicting Breast Cancer Using Logistic Regression and Multi-Class Classifiers”. International Journal of Engineering & Technology

   20. (2018): 22–22. https://www.researchgate.net/publication/331233978\_Predicting\_Breast\_ Cancer\_using\_Logistic\_Regression\_and\_Multi - Class\_Classifiers.
1. Sarthak Vyas, Abhinav Chauhan, Deepak Rana, Noman Ansari et al. “Breast Cancer Detection Using Machine Learning Techniques.” International Journal for Research in Applied Science & Engineering Technology (IJRASET) (2022): https://www.researchgate.net/publication/361024112\_Breast\_Cancer\_Detection\_Using\_Mach ine\_Learning\_Techniques.
1. Arpita Joshi and Dr. Ashish Mehta et al. “Comparative Analysis of Various Machine Learning Techniques for Diagnosis of Breast Cancer.” International Journal on Emerging Technologies (Special Issue NCETST) (2017): https://www.researchtrend.net/ijet/pdf/113-F-798.pdf
9. Abdullah-Al Nahid and Yinan Kong et al. “Involvement of Machine Learning for Breast Cancer Image Classification: A Survey”. International Journal of Engineering Research & Technology (IJERT) (2017). https://www.hindawi.com/journals/cmmm/2017/3781951/
9. Hiba Asri, Hajar Mousannif ,Hassan Al Moatassime, Thomas Noel et al. “Using Machine Learning Algorithms for Breast Cancer Risk Prediction and Diagnosis.” The 6th International Symposium on Frontiers in Ambient and Mobile Systems (FAMS 2016): https://www.sciencedirect.com/science/article/pii/S1877050916302575?ref=pdf\_download &fr=RR-2&rr=7f414817ec9e3ffb
9. Dana Bazazeh and Raed Shubair et al. “Comparative Study of Machine Learning Algorithms for Breast Cancer Detection and Diagnosis.”: https://www.researchgate.net/publication/310589496\_Comparative\_Study\_of\_Machine\_Le arning\_Algorithms\_for\_Breast\_Cancer\_Detection\_and\_Diagnosis
9. Md. Mehedi Hassan, Md. Mahedi Hassan, Farhana Yasmin, Md. Asif Rakib Khan, Sadika Zaman, Galibuzzaman, Khan Kamrul Islam, Anupam Kumar Bairagi et al. : “A comparative assessment of machine learning algorithms with the Least Absolute Shrinkage and Selection Operator for breast cancer detection and prediction.” https://www.sciencedirect.com/science/article/pii/S2772662223000851
19
