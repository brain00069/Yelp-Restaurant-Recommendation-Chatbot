# Yelp-Restaurant-Recommendation-Chatbot

## Introduction
The rise of AI agents in search engines has marked a transformative shift in how people interact with information online – users no longer want to waste time filtering through all the noise to find the information they need. A 2025 Gartner study depicts that “30% of online queries will be handled by AI assistants by 2026, driven by users' preference for direct answers over manual link-clicking”. 1 This statistic is only increasing and is generating a “zero click” search trend, as users desire immediate solutions.

The most important aspect of any major recommendation system is ease of user and accessibility for the user. For this reason, this project will focus on bringing the numerous and intricate data of the popular business review platform, Yelp, to the forefront of user interaction with a chatbot. Yelp is a business that runs primarily on crowd-sourced reviews from across the globe, often focusing on businesses such as restaurants, clubs, and retailers. Many users frequent the website and attempt to navigate it using keywords that are often accompanied by multiple clicks and time wasted attempting to find answers to their questions such as the dietary composition of a certain restaurant, a local park’s operating hours, or the location of their favorite fashion store. At this time, Yelp currently maintains a chatbot for services, but it does not include functionality for restaurants. The creation of this chatbot aims to address these concerns, by making the publicly-available data on the Yelp website to converse with a user about their needs and expectations regarding businesses of interest.

## Data Overview & Pre-Processing
The data acquired in this project was sourced from the Yelp Open dataset, which was a comprehensive dataset that includes reviews, business details, user data, and photos. This dataset included over 7 million reviews from over 150,000 businesses across Yelp – a staggering amount of data. This challenge motivated the project’s focus, which aimed to make searching for these restaurants and businesses easier for the user. First, we extracted the data from the JSON file and converted it to a csv file.

The Yelp Open Source file contained numerous files, but we narrowed down our project down to two datasets that were related to the business and their respective reviews. The pre-processing pipeline began with merging the business and reviewing datasets on the ‘business_id’ column and the following attributes were kept in our dataset:

### Data Dictionary
1. Business ID - The unique identifier for each business on Yelp. Review and business datasets were merged on this column.
2. Text - The text content of the review, what the customer wrote about the experience.
3. Date - The date the review was posted.
4. Name - The name of the business being reviewed.
5. Address - The address of the business being reviewed.
6. City - The city where the business is located.
7. State - The state where the business is located.
8. Postal Code - The postal code where the business is located.
9. Latitude - The latitude of where the business is located.
10. Longitude - The longitude of where the business is located.
11. Stars_y - The overall stars given to a business calculated over the total amount of reviews.
12. Review Count - The number of reviews posted in this dataset.
13. Attributes - This describes the business characteristics.
14. Categories - A list of categories that the business falls under.

Between the reviews and the business datasets, we removed the following columns: stars (the individual stars given to the restaurant by a specific reviewer), whether the restaurant was open at the time this dataset was created, and emotions to reviews such as “funny”, “cool”, and “useful”.

In addition, rows where the text, restaurant name, or categories were missing were effectively removed from the dataset. To standardize language usage, we applied tokenization and lemmatization, refining user reviews into a structured format that reduced words to their base forms and eliminated unnecessary noise. By ensuring data integrity and consistency, the final dataset enhanced chatbot performance, enabling accurate and personalized restaurant recommendations based on clean and reliable data.

## Exploratory Data Analysis/Visualizations
![image](https://github.com/user-attachments/assets/aaf0c847-63c9-4bd0-8967-8080b9bcd870)

• Perhaps unsurprisingly, the most popular types of businesses in the dataset were restaurants, or some sort of food variation, however, one thing that surprised the group was that Shopping and Home Services were categories that were somewhat nor far behind these powerhouses on the Yelp platform. This makes sense since most people use Yelp to look at review ratings and recommendations for restaurants.


![image](https://github.com/user-attachments/assets/9fab8042-ab60-4ee7-940b-ed51ab2ab50a)

• We noticed that in our dataset, American Restaurants and Bars and Pubs were the most prevalent, followed by Mexican, Pizza, and Chinese Restaurants. Despite this, the ‘Other’ category was by far the most prevalent, highlighting the variety of culinary business types present within our dataset.


![image](https://github.com/user-attachments/assets/e7ff3dba-645e-4671-a3f7-0136036b7ce0)

• Negative reviews primarily focus on poor service, words like “never”, “problem”, “issue” and “customer service” appear frequently, indicating dissatisfaction with the service or experience which often results in customers choosing not to return.


![image](https://github.com/user-attachments/assets/12431bb1-05a1-4b73-b94f-f1bea50131e1)

• Positive reviews are filled with words like "highly recommend", "great place", "amazing atmosphere" and "definitely coming back." Customers frequently praise friendly service and enjoyable experiences, using phrases with strong expressions, indicating that excellent experiences drive customer satisfaction.

## NLP Approaches & Methodologies
To make our chatbot actually useful for recommending restaurants, we utilized some Natural Language Processing (NLP) techniques to understand and match user queries with relevant business reviews.
1. TF-IDF
2. RAG (Retrieval-Augmented Generation)
3. Alltius Implementation

## Reflection
From this project, we learned that utilizing Natural Language Processing to create a Chatbot is an intricate and highly complex process that involves careful handling of unstructured data, thoughtful model selection, and iterative experimentation to balance accuracy, scalability, and user experience. Immediately, we observed that the most difficult part of working with unstructured data is being able to deal with the data itself. After much trial and error, we successfully read the massive, unstructured dataset into a Python notebook to begin analysis. Following this, we were able to implement many of the Natural Language Processing tools learned in class, including TF-IDF vectorization, sentiment analysis, cosine similarity, Retrieval-Augmented Generation, and much more within the creation of the chatbot in Alltius.

Ultimately, despite these challenges, this project highlighted the tradeoff between different NLP techniques: TF-IDF was computationally efficient, it lacked true semantic understanding. However, RAG improved the accuracy by incorporating vector search, and Alltius provided better contextual awareness. However, RAG and Alltius both came with computational and scalability challenges, as working with large datasets made it difficult to achieve goal over the totality of the dataset.To iterate on the limitations and challenges we faced, some next steps would involve implementing a full RAG pipeline that passes the reviews into GPT4 to create a true conversational and generative chatbot. 

## Conclusion
The goal of the project was to build a chatbot that uses the Yelp Open Dataset to provide personalized restaurant recommendations and answer user queries. Utilizing a five-step process, the group ensured that this goal was met by;
1. Gathering and cleaning the open-source Yelp dataset
2. Conducting exploratory data analysis and visualizations in order to single out any trends or necessary stopwords to include in our model creation
3. Conducting TF-IDF, Cosine Similarity, Retrieval-Augmented Generation, and Alltius model training to ensure accuracy and succinctness
4. Focusing on the front-end framework to create a clean and visually appealing prompt interface so that the user feels comfortable asking their query
5. After getting artificial model accuracy results, conducting real-world implementation by asking others to try the ChatBot for themselves

Ultimately, this project successfully illustrated the potential of Natural Language Processing to transform user interactions on review platforms like Yelp. By leveraging these advanced techniques, the final accuracy we achieved was 80%, which significantly outperformed basic methods like TF-IDF. Future work could explore the integration of conversational AI to further enhance the chatbot’s capabilities within the RAG implementation and training the chatbot with additional datasets for the Alltius implementation. As a result, this project achieves the immediate goals and highlights the critical role of NLP techniques in enhancing the user experience by providing personalized and context aware recommendations.
