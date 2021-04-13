# National-Park-Sentiment-Analysis
![National Park SA Banner](https://user-images.githubusercontent.com/69167875/114478413-cc183a80-9bc3-11eb-8226-57e965e255e8.png)

## **Problem Statement**
### How do people feel about the National Park Service?

To explore this question, I have set up a sentiment analysis on select parks in the National Park Service using tweets gathered from Twitter. 

As the park system continues to experience increasing visitor numbers, diving into a sentiment analysis can be beneficial when gauging public opinion. This information could be especially helpful as the National Park Service adjusts and adapts to new pressures in a COVID-19 world. 

## **Data Collection & Parameters**
Data for this project was gathered using Twitter’s API paired with Twython—a Python wrapper that works with Twitter’s API. I selected Twitter’s standard search API which—at the time of this project—allows developers to query a collection of tweets over the previous seven days. 

My [initial data collection](National_Park_SA_Initial_Data_Collection.ipynb) focused on five park-specific hashtags and one hashtag utilized by the official National Park Service Twitter page: #gsmnp, #GrandCanyon, #rmnp, #ZionNPS, #Yosemite, #NPS. This initial data collection yielded a relatively small number of tweets, with many unrelated to the park system. I modified my search, and expanded to ten hashtags: #gsmnp, #GrandCanyon, #rmnp, #ZionNationalPark, #Yosemite, #AcadiaNationalPark, #GrandTeton, #OlympicNationalPark, #GlacierNationalPark, #NPS. [This combination produced a higher number of relevant tweets for analysis](National_Park_SA_Additional_Data_Collection.ipynb). 

Twitter data was collected across a period of three weeks in 2020; the final week of November, and two weeks of December. This time period included two holidays and three weekends, which typically see higher visitor turnout. The results of each collection was saved as a separate CSV. 

### Queried National Parks & 2019 Visitation Numbers
<img width="530" alt="NationalParkChart1" src="https://user-images.githubusercontent.com/69167875/114486017-9c246380-9bd2-11eb-87ac-ce129b800875.png">

## **Data Cleaning & Processing**
[Multiple cleaning and processing steps were required before moving forward with analysis](National_Park_SA_Final_Processing.ipynb). For this stage of the project, I heavily relied on the Natural Language Toolkit (nltk). 

### Cleaning
- Separated tweets from other Twitter data
- Converted tweets to lowercase text
- Removed any duplicated tweets
- Converted emojis to their text description using demoji
- Removed all remaining non-alphanumeric characters

### Processing
- Tokenized the cleaned tweets
- Removed stop words such as "is" and "in"
- Lemmatized the tokenized tweets
- Created frequency distributions of the final tweet data
- Utilized nltk's SentimentIntensityAnalyzer on the cleaned pre-tokenized tweets

## **Visualizations**

### Word Frequency - Twenty-Five Most Common Words
![Twenty-Five Most Common Words](https://user-images.githubusercontent.com/69167875/114479747-bce6bc00-9bc6-11eb-85b4-cf18ac49839e.png)

### Word Cloud
![Word Cloud](https://user-images.githubusercontent.com/69167875/114479777-ca03ab00-9bc6-11eb-811c-96086a6cb916.png)

### Sentiment Analysis Scores
<img width="563" alt="SentimentAnalysis" src="https://user-images.githubusercontent.com/69167875/114487116-a47d9e00-9bd4-11eb-8a97-7c50d455ed3e.png">

## **Analysis**
The results of the sentiment analyzer revealed that overall, the collected Twitter data showed a neutral-to-positive response to the National Park Service. 

This is somewhat expected, as a number of the most frequently appearing words in the dataset were interpreted as “neutral.” For example, some of the most commonly appearing words like “mountain” and “park” are processed as neutral and have no negative or positive connotation. Further, the cleaned Twitter data also contained stop words that would be assigned a neutral value. If you examine just the negative score and the positive score of the sentiment analysis, the overall general opinion of the parks is a positive one. 

## **Takeaways & Future Research**
Overall, the public has a neutral-to-positive response to the National Park Service.

For a more well-rounded analysis, it would be helpful to have a greater number of available tweets. This could be accomplished by adding additional search criteria, and expanding the number of parks included in the query. 

Ideally, it would also be beneficial to collect this information year-round. Several of the parks experience dips in visitor turnout as the seasons change, and continual data collection may help offset these fluctuations. For this project, data was collected in the winter months when some of the most popular parks exhibit some of the lowest turnout numbers.

For future research, it may also be beneficial for the park system to deploy a large-scale survey of park visitors and make that information publicly available. In conjunction with a sentiment analysis of Twitter data, this information could be helpful in completing a more comprehensive gauge of public opinion.

## **Tools & Documentation**
 For this project, the following tools were used:
 - Twitter Standard Search API
   - [Associated Documentation](https://developer.twitter.com/en/docs/twitter-api/v1/tweets/search/overview)
 - Twython
   - [Associated Documentation](https://twython.readthedocs.io/en/latest/)
 - Natural Language Toolkit (nltk)
   - [Associated Documentation](https://www.nltk.org)
 - demoji
   - [Associated Documentation](https://pypi.org/project/demoji/)
 - WordCloud
   - [Associated Documentation](https://amueller.github.io/word_cloud/)
