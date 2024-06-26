# Final Project Summary: Predicting Car Crash Probability Using Honda Consumer Complaints

### General Objectives

This project aims to build and test a predictive model for car crashes using consumer complaints data from Honda. The analysis leverages SAS Enterprise Miner (SAS EM) and Python to create a decision tree model that predicts the likelihood of car crashes. The key features considered include car model, manufacturing year, presence of anti-brake system, cruise control, miles per hour, overall mileage, complaint topics, and sentiment.

### Descriptive Statistics
The dataset consists of 5330 complaints, with approximately 10.7% reporting a crash. Key attributes include car make, model year, anti-brake system presence, cruise control, miles per hour, and overall mileage. Complaints are categorized into seven topics based on description, and sentiment analysis is performed to determine the average sentiment score for each complaint.

## Analytical Approach

### SAS EM Approach

1. **Topic Analysis** : Data preprocessing involved handling outliers and imputing missing values. Text mining identified seven major topics from customer complaints: Airbag, Brake and Acceleration, Headlight, Mileage, SRS Light, Tire, and Transmission.

2. **Text Sentiment**: Sentiment analysis was conducted using a predefined sentiment-words list, yielding an average sentiment score of -1.24, indicating predominantly negative feedback.

3. **10-Fold Cross Validation**: Various decision tree depths were tested to find the optimal configuration. For the data merged with the Text Topic node, a depth of 15 was optimal, while a depth of 14 was best for the Text Cluster result.

4. **Final Model Using 70/30 Cross Validation**: The best-performing model was the Non-HP decision tree using the Text Topic approach with the Entropy configuration for nominal targets.


### Python Approach

1. **Topic Analysis**: NLTK was used for text analytics. The complaints were preprocessed to handle synonyms and tokenized. TF-IDF was used to obtain the term-frequency matrix, and TruncatedSVD defined seven topics.

2. **Sentiment Analysis**: Sentiment scores were calculated without removing stop words to retain sentiment expressions.


3. **Decision Tree Model Analysis**: Attributes were encoded, and 10-fold cross-validation was used to select the best tree depth. The decision tree with a depth of 8 had the best performance.


## Web Scraping for 'Takata'

Python was used to scrape news articles related to Takata, identifying significant negative sentiment and public discourse due to safety issues with Takata airbags.

### Results

1.  **SAS EM Decision Tree**: The Non-HP decision tree using the Entropy configuration and Text Topic approach had the best performance, with low misclassification rate and high specificity, precision, and accuracy, but lower recall.

2. **Python Decision Tree**: The decision tree with a depth of 8 showed optimal performance with favorable metrics.


### Observations and Conclusions

- The Airbag topic was found to be the most significant predictor of crashes.

- Given the negative press surrounding Takata, it is recommended that Honda reassesses its relationship with Takata and enforces stricter quality assurance standards to protect its brand image.

- This project demonstrates the effectiveness of using both SAS EM and Python for predictive modeling and text analytics in identifying key factors contributing to car crashes.


### Appendix
Supporting images and additional documentation are included in the project repository to provide further insights into the analysis methods and results.
