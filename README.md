# Predicting Car Crash Probability Using Honda Consumer Complaints

### General Objectives

This project aims to build and test a predictive model for car crashes using consumer complaints data from Honda. The analysis leverages SAS Enterprise Miner (SAS EM) and Python to create a decision tree model that predicts the likelihood of car crashes. The key features considered include car model, manufacturing year, presence of anti-brake system, cruise control, miles per hour, overall mileage, complaint topics, and sentiment.

This project was submitted as part of a class project I submitted for STAT 656 : Applied Analytics taught by Edward Jones at Texas A&M University - College Station in 2018.

**Note: SAS Enterprise Miner has paid subscription which was provided through my school. If you are interested in replicating the same SAS results, please reach out and I can provide the ".sas7bdat" files used in this project**

### Descriptive Statistics
The dataset consists of 5330 complaints, with approximately 10.7% reporting a crash. Key attributes include car make, model year, anti-brake system presence, cruise control, miles per hour, and overall mileage. Complaints are categorized into seven topics based on description, and sentiment analysis is performed to determine the average sentiment score for each complaint.

## Analytical Approach

### SAS EM Approach

1. **Topic Analysis** : Data preprocessing involved handling outliers and imputing missing values. Text mining identified seven major topics from customer complaints: Airbag, Brake and Acceleration, Headlight, Mileage, SRS Light, Tire, and Transmission.

    ![SAS EM1](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/fb36b256-2b1a-473e-88f6-210ee6a7cd35)

2. **Text Sentiment**: Sentiment analysis was conducted using a predefined sentiment-words list, yielding an average sentiment score of -1.24, indicating predominantly negative feedback.

    ![SAS EM2](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/eee76b75-4a81-4922-a1f4-49fb9413fe50)

    ![SAS EM3](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/c9209434-a08e-4959-8e0b-29fce53e0ad8)

3. **10-Fold Cross Validation**: Various decision tree depths were tested to find the optimal configuration. For the data merged with the Text Topic node, a depth of 15 was optimal, while a depth of 14 was best for the Text Cluster result.

    ![SAS EM4](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/0d9169f8-13a8-46ea-a1eb-7570c90de211)

    ![SAS EM5](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/301ea77c-a5aa-488c-b176-42ffc7fc37b6)

4. **Final Model Using 70/30 Cross Validation**: The best-performing model was the Non-HP decision tree using the Text Topic approach with the Entropy configuration for nominal targets.

    ![SAS EM7](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/ead486aa-6a7c-4773-b17d-fb5d786e33e5)

    ![SAS EM6](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/88b0cfc1-2e77-4508-b7f8-80f8620d8e70)


### Python Approach

1. **Topic Analysis**: NLTK was used for text analytics. The complaints were preprocessed to handle synonyms and tokenized. TF-IDF was used to obtain the term-frequency matrix, and TruncatedSVD defined seven topics.

    ![SAS EM8](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/1f2f1043-b68a-4d99-85ae-2ebc05b8dede)

2. **Sentiment Analysis**: Sentiment scores were calculated without removing stop words to retain sentiment expressions.


3. **Decision Tree Model Analysis**: Attributes were encoded, and 10-fold cross-validation was used to select the best tree depth. The decision tree with a depth of 8 had the best performance.

    ![Python1](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/93265373-16c6-46f9-b702-35aca59c08b0)

    ![Python2](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/3127482c-d21d-4021-915b-10563115f9ae)

    ![Python3](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/4327484a-0a99-4cd8-9bad-30720ec3b542)


## Web Scraping for 'Takata'

Python was used to scrape news articles related to Takata, identifying significant negative sentiment and public discourse due to safety issues with Takata airbags.

### Results

1.  **SAS EM Decision Tree**: The Non-HP decision tree using the Entropy configuration and Text Topic approach had the best performance, with low misclassification rate and high specificity, precision, and accuracy, but lower recall.

    ![SAS EM9](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/18be89f9-8e15-42ce-ad25-2a229858fd75)

2. **Python Decision Tree**: The decision tree with a depth of 8 showed optimal performance with favorable metrics.

    ![Python4](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/c70697aa-8009-46c7-bdaf-58bb3b882373)


### Observations and Conclusions

- The Airbag topic was found to be the most significant predictor of crashes.

- Given the negative press surrounding Takata, it is recommended that Honda reassesses its relationship with Takata and enforces stricter quality assurance standards to protect its brand image.

- This project demonstrates the effectiveness of using both SAS EM and Python for predictive modeling and text analytics in identifying key factors contributing to car crashes.

    ![Python5](https://github.com/MrlWallis/sentiment_analysis/assets/36977382/5ea11e6a-b943-47f3-9147-e64293918e68)

### Appendix
Supporting images and additional documentation are included in the **APPENDICES - HONDA COMPLAINTS.doc** file to provide further insights into the analysis methods and results.

Feel free to reach out if you have any questions/suggestions or ideas for a project. Thanks for reading!
