# Step 1) Data Collection
See [data_collection](./data_collection/Data%20Collection.ipynb) for more details.

Used [snscrape](https://github.com/JustAnotherArchivist/snscrape) to scrape Twitter advanced search results and collected tweets with #covid hashtag.

Overall scraping covid related tweets from 11-February-2020 to 24-May-2023 took around ~6 hours to complete, and collected around ~305.3K tweets.

Tweets are saved in different files to mimic a big data dataset, for example: [February-2020](./data_collection/2020-02.csv) data.

# Step 2) Sentiment Analysis
See [data_sentiment_analysis](./data_sentiment_analysis/AddSentiments.ipynb) for more details.

Reads data_collection save files, and uses [NLTK](https://www.nltk.org/) provided Sentimeny Analyzer [VADER](https://www.nltk.org/_modules/nltk/sentiment/vader.html) to score sentiment polarities of tweet contents. Tweets files are saved in [data_sentiment_analysis/data](./data_sentiment_analysis/data) directory to not override raw collected data.

This step adds 4 new columns to dataset:
* pos: Positive polarity score of the text between 0 to +1
* neu: Neutral polarity score of the text between 0 to +1
* neg: Negative polarity score of the text between 0 to +1
* compound: Compound polarity score of the text between -1 to +1 (-1 being negative and +1 being positive)

# Step 3.1) Database Benchmarking Comparison
See [ycsb_database_benchmark](./ycsb_database_benchmark/Compare%20Databases.ipynb) for more details.

Used [Yahoo! Cloud Serving Benchmark (YCSB)](https://github.com/brianfrankcooper/YCSB) to benchmark MongoDB and Postgred SQL.

[YCSB 0.17.0](https://github.com/brianfrankcooper/YCSB/releases/tag/0.17.0) version bindings in [ycsb-mongodb-binding-0.17.0.tar.gz](./ycsb_database_benchmark/ycsb-mongodb-binding-0.17.0) and [ycsb-postgrenosql-binding-0.17.0.tar.gz](./ycsb_database_benchmark/ycsb-postgrenosql-binding-0.17.0) are used, to benchmark 'basic' workload with load and run commands: [see bat file](./ycsb_database_benchmark/ycsb-mongodb-binding-0.17.0/basictest.bat).

# Step 3.2) MongoDB and MapReduce
See [data_mongo_mapreduce](./data_mongo_mapreduce/MongoDB_MapReduce.ipynb) for more details.

# Step 4.1) Time Series Analysis
See [time_series_analysis](./time_series_analysis/Analysis.ipynb) for more details.

# Step 4.2) Time Series Forecasting
See [time_series_forecasting](./time_series_forecasting/Forecast.ipynb) for more details.