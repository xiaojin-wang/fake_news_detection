# Readme.md 

This is the description of the project code of CS5344. 

## Data Source 

Note: the complete dataset cannot be distributed due to the privacy policies and restrictions of Twitter

And the tool we use to download data: FakeNewsNet: https://github.com/KaiDMML/FakeNewsNet 

The structure and size of our downloaded raw data: 

├── gossipcop (3.71GB) 

│   ├── fake (1.37GB; 5,523 items; name: source-newsid) 

│   │   ├── gossipcop-2116458 

│   │	│	├── news content.json 

│   │	│	├── tweets 

│   │	│	│	├── 886941526458347521.json 

│   │	│	│	├── 887096424105627648.json 

│   │	│	│	└── ....		 

│   │	└── ....			 

│   └── real (2.34GB; 16,817 items; name: source-newsid) 

│      ├── gossipcop-541230 

│      │	├── news content.json 

│      │	├── tweets 

├── politifact 

│   ├── fake (650.3 MB; 432 items; name: source-newsid) 

│   │   ├── politifact-11773 

│   │   │	├── news content.json 

│   │   │	├── tweets 

│   │ 

│   └── real (938.9 MB; 624 items; name: source-newsid) 

│      ├── politifact-7 

│      │	├── news content.json 

│      │	├── tweets 

│      └── ....					 

├── user_profiles (1.55GB; 463,119 items; name: user_id) 

│		├── 620333.json 

│		├── 5867882.json 

│   		└── .... 

 

## Code Structure: 

Name convention of models code, modelName_dataDimension(_newsSource) 

Example: LR_tweets_gossipcop.ipynb: Logistic Regression Model on tweets in GossipCop 

Noted: (_newsSource) because the experiments were completed for both Politifact and Gossipcop in the same notebooks (by changing input csv name, etc.) 

-Project 

--Data Integration 

- gosscipcop_news.ipynb: merge json files of news from Gossipcop into one csv 

- gosscipcop_tweets.ipynb: merge multiple csv files of tweets related to the news from Gossipcop into one csv 

- merge_tweets_to_csv.ipynb: merge json files of tweets in Gossipcop and PolitiFact into csv 

- merge_user_profile.ipynb: merge json files of user profiles into csv 

- politifact_news.ipynb: merge json files of news from PolitiFact into one csv 

- politifact_tweets.ipynb: merge multiple csv files of tweets related to the news from PolitiFact into one csv 

- tweets_with_users.ipynb: join user profiles and tweets by ‘user_id’ 

--Data Preprocessing 

- gossipcop_tweets_preprocessed.ipynb: preprocess attributes including ‘created_at’, ‘favorite_count’ and ‘retweet_count’ in gosscipcop_tweets.csv 

- politifact_tweets_preprocessed.ipynb: preprocess attributes including ‘created_at’, ‘favorite_count’ and ‘retweet_count’ in politifact_tweets.csv 

--EDA 

- EDA of GossipCop.ipynb 

- EDA of PolitiFact.ipynb 

- word cloud.ipynb 

--Step1 Simple News Content Classification 

- LR_news.ipynb 

- GBT_news.ipynb 

- RandomForest_news.ipynb 

- Longformer_news.ipynb 

--Step2 Multi-dimensional Tweets Classification 

- LR_tweets_gossipcop.ipynb 

- LR_tweets_politifact.ipynb 

- GBT_tweets_gossopcop.ipynb 

- GBT_tweets_politifact.ipynb 

- RandomForest_tweets.ipynb 

- Longformer_tweets.ipynb 

--Step3 Multi-dimensional User-based Classification 

- LR_users.ipynb 

- GBT_users.ipynb 

- RandomForest_users_gossipcop.ipynb 

- RandomForest_users_politifact.ipynb 

- Longformer_users.ipynb 