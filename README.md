# WeRateDogs Wrangling Report
## by Isiaq Adebayo Okeyode


## Dataset

The data was gotten from three sources and in different format respectively. The first data I used was the Twitter 
Archive data even though it was downloaded programmatically by Udacity and provided to me in a csv format to download 
manually, I still used GET requests to download it using the URL: 
'https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv' 
and it was saved to the directory I created (file_name). It was read into a pandas dataframe (twt_arc) using pandas read_csv.

The second data I used was the Image Predictions Data provided by Udacity in a URL: 
'https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv' which I 
programmatically downloaded using the Python Requests library. I created folder for the file then use GET requests to download 
it from the URL. I opened the file in the folder and read the file into pandas data frame (img_prd).

Due to some missing values in the Twitter Archive table, I decided to query Twitter account WeRateDogs for additional information 
such as (tweet_id, retweet_count, and favourite_count) using Twitter API called TWEEPY. I applied for a Twitter Developer account, 
but I didn't get the necessary keys needed on time because of some technical difficulties with my Twitter account so I used the 
file provided by Udacity Platform (tweet-json.txt). I only needed more information from tweet ids I already had in Twitter Archive 
Data frame. I created an empty list called df_list to append the data to, I opened the tweet-json.txt file in read format and for 
each line loaded it to a variable. I accessed this variable to get the tweet_id, retweet_count and favourite count values. 
Then, I appended this to the empty list (df_list) I initially created. I converted this list to a data frame (twt_json) using pd.DataFrame. 



## Summary of Findings

In the exploration, I found that there was a strong relationship between retweet and likes, tweets with plenty retweet will surely garner 
more likes (our r = 0.786 which is close to 1 according to pearson correlation coefficient).

It was also observed that the top 3 dog_stages to receive the most likes (favorite_count) are doggo,puppo with more than 40,000+ likes, 
followed by puppo with 20,000+ likes and doggo with 18,000+ likes.

It is likely that tweet from an Iphone gathers more likes, but it is worthy to note that there are other factors that could be at play 
such as contents of the tweet.

