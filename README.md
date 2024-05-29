# Assessment 4 - Unit PRT564 - Group 7 - Charles Darwin University

# Duel Analysis of Research Paper Retractions: Historical Patterns and Future Predictions

## Link to our presentation video
https://www.youtube.com/watch?v=vyTir18D_rw

## Problems
The increase in the number of scientific papers that are being withdrawn has become a significant concern and research focus in the past few years. The medical literature has seen many retractions, with a study by Steen (2011) estimating that flawed research puts patients at significant risk. Van Noorden's article Nature (2023) revealed that over 10,000 research papers were retracted in 2023 alone. If not retracted, flawed papers can mislead subsequent research, waste resources, and potentially lead to harmful real-world applications and policies based on incorrect findings.

## Objectives
There are two primary objectives driving this project:
- Explore relevant patterns, interesting, and actionable trends of past retractions.
- Predict important aspects of future retractions.

## Datasets
- The dataset “retractions35215.csv” is from “Retraction Watch” organisation.

- The dataset contains: 35215 rows and 21 columns.  

- Last updated: 15 Jan 2024

We also used another dataset collected from "Retraction Watch" database to validate the models. 

For more information: https://retractionwatch.com/retraction-watch-database-user-guide/retractionwatch-database-user-guide-appendix-a-fields/

Send us a request if you want to get the datasets.

## Methodology
Our methodology begins by handling a dataset comprised of retraction records. We start with data wrangling, which includes cleaning and transforming the data, as well as encoding it for further analysis. Initially, we experimented with one-hot encoding and target encoding. However, these methods were unsuitable as they increased the dataset's dimensionality and led to overfitting. Consequently, we opted for frequency encoding and label encoding for the nominal features and ordinal encoding for the ordinal response variable, 'LevelOfSeriousness'.

To meet our second objective, we conducted preliminary research to precisely define the 'LevelOfSeriousness' as the response variable for our classification models. We then performed exploratory data analysis (EDA) to uncover patterns and intriguing trends, fulfilling our first objective.

In addition to EDA, we used clustering techniques such as K-means and K-modes, combined with Principal Component Analysis (PCA), to identify clusters within the data. After the data mining process, we came up with a few more new features based on findings from EDA, these were part of feature engineering. We also did some research and found some relevant features such as 'H index', 'SJR' and 'SJR Best Quartile'. For our second objective, we developed various classification models, beginning with a Naive Bayes model as our baseline. To address data imbalances, we applied techniques like SMOTE and undersampling before proceeding with the models.

Following Naive Bayes, we tested other models including K-Nearest Neighbors (KNN), Random Forest (RF), Support Vector Machines (SVM), and Gradient Boosting Machines (GBM), with Standardisation method for accuracy improvement. After evalujating the models using metrics like accuracy, precision, recall and F1-score, the Random Forest model emerged as the most effective, particularly after implementing SMOTE for data balancing. We also ran the Random Forest model on each cluster to find the hidden insights from retractions that are similar to each other.

We integrated 5-fold cross-validation in our modeling process to ensure robustness and reliability. Then, we optimise the Random Forest model by finding the optimal settings for the model using Random Search and Grid Search. Finally, to validate our models, we sourced new data from the Retraction Watch database. This comprehensive approach allowed us to develop and refine predictive models effectively.

## Results
The best model is Random Forest with accuracy of 79.1% on the test set and 61% on the new dataset. The model was built with 12 predictors: 'IsPaywalled', 'IsInternationalCollaboration', 'Institution', 'ArticleType', 'Country', 'Author', 'CitationCount', 'Subject', 'Journal', 'TimeToRetraction', 'ArticleAge', 'Publisher'.

Patterns and trends:
- Subjects related to Biology and Technology have the most retractions.
- China has the most retractions with the persentage of 49.3%, more than other countries.
- Japanese and Chinese authors are on top of the list who has the most retractions.
- Department of Anesthesiology, Showa University Hospital, Tokyo, Japan has the most retractions.
- IEEE: Institute of Electrical and Electronics Engineers has the most retractions.
- Research Article and Conference Abstract/Paper are the most common article types of retractions.
- 87.2% of retractions is not a product of international collaboration.
- 5 most common reasons of retractions: Investigation by Journal/Publisher, Notice - Limited or No Information, Unreliable Results, Concerns/Issues About Data, Investigation by Third Party.
- In the past, most retractions were due to less serious reasons, while recently (2019-2024), the number of more serious retractions have gone up drammatically. Covid-19 might be a reason why researchers rushed to publish their papers, leading to a lot of mistakes made.
- These are the journals that have the most serious retractions:Journal of Physic: Conference Series; PLoS One; Journal of Ambient Intelligence and Humanized Computing; Arabian Journal of Geosciences; ICIMTECH 21: The Sixth International Conference on Information Management and Technology.
- Springer has the most serious retractions.
- The most serious retractions are reseach articles with 78.6%, which is 7655 retractions.
- The most common reasons for the most serious retractions are: Investigation by Journal/Publisher and Fake Peer Review. Therefore, implementing more transparent peer review processes, and using technological tools to detect fraud can help maintain the integrity of scientific publications.
- In 2022, Computer Science and Technology have a big number of the most serious retractions, while retractions of other subjects are slightly increasing.
- China has the most serious retractions in recent years, followed by India.
- Research Article has the most serious retractions in recent years, followed by Conference Abstract/Paper.

Models and predictions:
- Each centroid represents a distinct cluster with specific characteristics regarding the subject, institutions, retraction reasons, citation counts. 

Centroid 23299: High-impact biological and medical research with severe misconduct, often involving international collaboration. 

Centroid 20013: Focused on cellular biology and genetics with methodological issues, primarily from single institutions. 

Centroid 34487: High-impact biochemical research with serious ethical violations, mostly from India. 

Centroid 12675: Interdisciplinary research with issues of plagiarism, involving significant international collaboration between China and Pakistan. 

- The results were quite good, giving high numbers of correct predictions, with an accuracy of 78.41%, precision of 79.56%, recall of 78.48% and 78.65% F1 score on the test data.
- It is clear to see that there are some features which are always in top 5 of the most significant features to the level of seriousness: Journal, TimeToRetraction, Publisher, Country and ArticleAge.
  
There are more patterns and trends unpacked to see in the analysis file. Feel free to explore!

## Installation and usage guide
Run the 'requirements.txt' file to install necessary packages: **pip install -r requirements.txt**

matplotlib==3.5.1

numpy==1.22.3

pandas==1.4.1

scipy==1.8.0

seaborn==0.11.2

scikit-learn==1.0.2

imbalanced-learn==0.9.0

prince==0.7.1

kmodes==0.11.1

## Acknowledgements
We'd like to express our gratitude to our lecturer Dr. Yakub Sebastian at CDU for his invaluable guidance and insights throughout this project and Prof. Andrew Ng for the inspirational machine learning course on Coursera.

## List of project participants and contacts
I spearheaded this project as the team leader, with the invaluable collaboration of three other members: Van Hieu Tran, Thi Minh Chau Pham (Chelsey) and Augustine Shaibu.

Any concerns or contributions you might have, please feel free to reach me through [email](lecongdoo3@gmail.com).

## References
Bholowalia, P., & Kumar, A. (2014). EBK-means: A clustering technique based on elbow method and k-means in WSN. International Journal of Computer Applications, 105(9). 

Database, R. W. (2024). http://retractiondatabase.org/RetractionSearch.aspx? 

Developers, G. (2023). Imbalanced Data, Machine Learning. https://developers.google.com/machine-learning/data-prep/construct/sampling-splitting/imbalanced-data

Dhiraj K. (2019, 14/6/2019). Top 4 advantages and disadvantages of Support Vector Machine or SVM.  https://dhirajkumarblog.medium.com/top-4-advantages-and-disadvantages-of-support-vector-machine-or-svm-a3c06a2b107

Elsevier. Measuring a journal’s impact. https://www.elsevier.com/researcher/author/tools-and-resources/measuring-a-journals-impact

Fang, F. C., & Casadevall, A. (2011). Retracted science and the retraction index. Infect Immun, 79(10), 3855-3859. https://doi.org/10.1128/iai.05661-11 

Fang, F. C., Steen, R. G., & Casadevall, A. (2012). Misconduct accounts for the majority of retracted scientific publications. Proceedings of the National Academy of Sciences, 109(42), 17028-17033. 

Feng, L., Yuan, J., & Yang, L. (2020). An observation framework for retracted publications in multiple dimensions. Scientometrics, 125(2), 1445-1457. 

Gnana, D. A. A., Balamurugan, S. A. A., & Leavline, E. J. (2016). Literature review on feature selection methods for high-dimensional data. International Journal of Computer Applications, 136(1), 9-17. 

Hemashreekilari. (2023, 5/9/2023). Understanding Gradient Boosting.  https://medium.com/@hemashreekilari9/understanding-gradient-boosting-632939b98764

Kapkar, B. (2020). Which Machine Learning requires Feature Scaling(Standardization and Normalization)? And Which not? Kaggle.com. https://www.kaggle.com/discussions/getting-started/159643

Kebede, S. D., Sebastian, Y., Yeneneh, A., Chanie, A. F., Melaku, M. S., & Walle, A. D. (2023). Prediction of contraceptive discontinuation among reproductive-age women in Ethiopia using Ethiopian Demographic and Health Survey 2016 Dataset: A Machine Learning Approach. BMC Medical Informatics and Decision Making, 23(1), 9. 

Lab, S. (2024). Scimago Journal Rankings. https://www.scimagojr.com/journalrank.php?year=2018

MLNerds. (2019, 14/2/2019). How does KNN algorithm work? What are the advantages and disadvantages of KNN? https://machinelearninginterview.com/topics/machine-learning/how-does-knn-algorithm-work-what-are-the-advantages-and-disadvantages-of-knn/

NIH Office of Portfolio Analysis. New Analysis iCite. https://icite.od.nih.gov/ 

Oludare, E. (2020, 27/11/2020). Random Forest: How it Work and Benefit. https://medium.com/analytics-vidhya/random-forest-algorithm-how-it-works-and-benefit-5ae40aab6ae0

Řezanková, H., & Everitt, B. (2009). Cluster analysis and categorical data. Statistika, 89(3), 216-232. 

Schneider, J., Ye, D., Hill, A. M., & Whitehorn, A. S. (2020). Continued post-retraction citation of a fraudulent clinical trial report, 11 years after it was retracted for falsifying data. 

Scientometrics, 125(3), 2877-2913. https://doi.org/10.1007/s11192-020-03631-1 

Scikit Learn. (2024). Cross-validation: evaluating estimator performance. https://scikit-learn.org/stable/modules/cross_validation.html

Seldon. (2021). Machine Learning Optimization - Why is it so Important? https://www.seldon.io/machine-learning-optimisation 

Shahraki-Mohammadi, A., Keikha, L., & Zahedi, R. (2024). Investigate the relationship between the retraction reasons and the quality of methodology in non-Cochrane retracted systematic reviews: a systematic review. Systematic Reviews, 13(1), 24. 

Sharma, P., Sharma, B., Reza, A., Inampudi, K. K., & Dhamija, R. K. (2023). A systematic review of retractions in biomedical research publications: reasons for retractions and their citations in Indian affiliations. Humanities and Social Sciences Communications, 10(1), 1-12. 

Szakal, F. D. (2021, 25/4/2021). Retracting publications doesn’t stop them from influencing science. https://www.salon.com/2021/04/25/retracting-publications-doesnt-stop-them-from-influencing-science_partner/

Van Noorden, R. (2023). More Than 10,000 Research Papers Were Retracted in 2023-a New Record. Nature, 624(7992), 479-481. https://doi.org/10.1038/d41586-023-03974-8 

Vujović, Ž. (2021). Classification model evaluation metrics. International Journal of Advanced Computer Science and Applications, 12(6), 599–606. 

Wray, K. B., & Andersen, L. E. (2018). Retractions in. Scientometrics, 117(3), 2009-2019. https://doi.org/10.1007/s11192-018-2922-4 

Xu, S., & Hu, G. (2022). A cross-disciplinary and severity-based study of author-related reasons for retraction. Accountability in Research, 29(8), 512-536. 

Zhao, T., Dai, T., Lun, Z., & Gao, Y. (2021). An analysis of recently retracted articles by authors affiliated with hospitals in mainland China. Journal of Scholarly Publishing, 52(2), 107–122.
