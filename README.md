# Twitter-Archive-Project
In this project, we work on the three datasets;

Enhanced Twitter Archive This is a WeRateDogs Twitter archive dataset which contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which was used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 5000+ tweets, we filtered for tweets with ratings only (there are 2356). This file is read into pandas as rating_puppies using the 'twitter-archive-enhanced.csv' provided by WeRateDogs.

The tweet image predictions This file is given as (image_predictions.tsv), hosted on Udacity's servers and it is downloaded programmatically using the Requests library from the following [URL]:(https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv). This image file is gotten when every image in the WeRateDogs Twitter archive is ran through a neural network that can classify breeds of dogs. This gives a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images). The columns in this file include; tweet_id, img_num, jpg_url, p1, p1_conf, p1_dog,p2, p2_conf, p2_dog, p3, p3_conf, and p3_dog, where;

tweet_id is the last part of the tweet URL after "status/"
p1 is the algorithm's #1 prediction for the image in the tweet → golden retriever
p1_conf is how confident the algorithm is in its #1 prediction → 95%
p1_dog is whether or not the #1 prediction is a breed of dog → TRUE
p2 is the algorithm's second most likely prediction → Labrador retriever
p2_conf is how confident the algorithm is in its #2 prediction → 1%
p2_dog is whether or not the #2 prediction is a breed of dog → TRUE etc.


Additional data from the Twitter API We gathered each tweet's retweet count and favorite ("like") count at the minimum and any additional data we find interesting. Using the tweet IDs in the WeRateDogs Twitter archive, by querying the Twitter API for each tweet's JSON data wiyh Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file.

Each tweet's JSON data were written to its own line. Then we read this tweet_json.txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count.
