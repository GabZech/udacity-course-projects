# About

The Twitter user @dog_rates, also known as WeRateDogs, is an account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10 and numerators greater than 10 such as 11/10, 12/10, 13/10. This humorous rating system is one of the reasons why WeRateDogs has over 4 million followers and has received international media coverage. 

This project focused on **gathering, assessing, and cleaning data from the @dog_rates Twitter account** and producing simple analyses and visualisations.

The data collection and processing can be seen in the [wrangle_act.ipynb](wrangle_act.ipynb/) jupyter notebook and the (very limited and simple) explanatory visualisations in the report [act_report.pdf](act_report.pdf/).


## Gathering data for this project

Data was collected through the following means:
1. **Twitter API access**: Using the tweet IDs in the WeRateDogs Twitter archive, I queried the Twitter API for each tweet's JSON data using Python's Tweepy library and stored each tweet's entire set of JSON data in a file called tweet_json.txt file. Each tweet's JSON data was written to its own line. Then this .txt file was read line by line into a pandas DataFrame with tweet ID, retweet count, favorite count and retweeted status.
2. **Python's Requests library:** the file containing predictions ([image_predictions.tsv](image_predictions.tsv/)) of what breed of dog (or other object, animal, etc.) is present in each tweet picture according to a neural network was hosted on online servers and was downloaded programmatically using the Requests library and the provided link.
3. **Manual download**: the file [twitter_archive_master.csv](twitter_archive_master/) contains a selection of tweets and was download manually from the internet.


## Assessing data for this project
By using programmatic methods, I assessed the three dataframes looking for inconsistencies, errors, duplicates, missing data and other problems with the data.
I thus made a list of 11 quality and 2 tidiness issues to be fixed. These were the following:

### Quality issues
*In the table 'tweet_archive'*
1. Data type in 'timestamp' column is string instead of datetime, and there should be columns for year,
month and day
2. There are 181 retweets - we only want original tweets with images
3. Columns [doggo, floofer, pupper, puppo] have "None" values instead of null values
4. Column 'name' has values 'None', 'a', 'an', 'the' and other wrong ones
5. There are rating_denonimator values other than 10 and wrong numerator values
6. Drop columns that won't be used for the analysis
In table tweet_predictions
7. Names in columns p1, p2 and p3 have different capitalisations
8. Only use first (stronger) prediction and rename the columns to 'prediction', 'confidence' and 'is_dog'
9. Drop duplicated jpg_url rows
10. Drop columns that won't be used for analysis
 
*In the table 'tweet_popularity'*

11. Drop 'retweeted' column

### Tidiness issues

*In the table 'tweet_archive'*
1. Mutliple columns for dog type variable (doggo, floofer, pupper, puppo)
2. Merge all tables

## Cleaning data for this project

After creating a copy of each dataframe, I went on to use common programmatic methods to clean
and fix those issues. Most of them were simple methods like pd.to_datetime, .replace(), .drop() and drop_duplicates(), .merge(), etc.

However, some of them were more challenging and included creating loops that analysed each row
and altered the data according to multiple conditions.
