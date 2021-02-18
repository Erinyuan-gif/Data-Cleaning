# WeRateDogs

This academic project was meant to analyze the most popular dogs on WeRateDogs and the score people rate for the cutiness of their dogs. 

The biggest challenge for this project was cleaning data and conducting a structured dataset for analysis. 

There are three datasets used for analysis: 
1. archived dataframe (twitter-archive-enhanced.csv): df
2. image dataframe: image_df
3. extracted from Twitter API: new_df
The final dataset after cleaning is (twitter_archive_master.csv) in the folder

Quality issues that I found:
1. missing values in these columns: in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp, expanded_urls.
2. contains rows that are retweets and replies
3. timestamp and retweeted_status_timestamp are string
4. the columns 'doggo, floofer, pupper, and puppo' have many 'None' values
5. the column 'name' contains invalid names, such as 'a', 'None'.
6. the rating denominator should not be 0.
7. the rating donominator is not standardized

To clean data, I did:
1. drop retweets and replies rows
2. remove data columns that are missing too many values
3. convert timestamp to date time
4. convert 'doggo, floofer, pupper, and puppo' to categorical values and create a new column to contain all categories
5. change invalid name to NaN
6. drop the line that has a rating_denominator of 0 since its numerator is too large
7. standerdize the ratings
8. leave the most accurate breed in image_df and cut the rest columns
9. standerdize the breeds spelling by lowering cases
10. merge image_df and new_df dataframes to the main dataframe df

Here are some conclusions from my analysis:

The top 10 popular breeds are golden retriever, labrador retriever, pembroke,chihuahua, pug, toy poodle, chow, samoyed, pomeranian,malamute.
The most popular breed 'golden retriever' has tweets that accounts for more than 7.5% of all the records in this dataset. The 10th popular breed 'malamute' has about 2% of total records.
However, the ratings of these breeds are similar and close to 11 out of 10. 'Pomerianian' has the highest rating among all 10 breeds.
