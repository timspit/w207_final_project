## Meta Data

"number_of_downvotes_of_request_at_retrieval" - (Sentiment) Maybe this could give us an idea about what people think about the request. People better at understanding emotions

"number_of_upvotes_of_request_at_retrieval" - (Sentiment)

"post_was_edited" - Could be removed

## "request_id" - IMPORTANT

"request_number_of_comments_at_retrieval" - Could be removed OR this could also go into (Sentiment)

"request_text" - Could be ignored for below variable? Posts are often edited after a successful request, this request_text column is not the most accurate.

## "request_text_edit_aware" - IMPORTANT Looks like, mostly this is same as request_text usually. Use this (Textual Feature) / Edit aware version of "request_text" strips edited comments indicating the success of the request

## "request_title" - IMPORTANT (Textual Feature)

## "requester_account_age_in_days_at_request" - Maybe, will have to do EDA to check vs success / failure and see if there is a pattern

"requester_account_age_in_days_at_retrieval"

## "requester_days_since_first_post_on_raop_at_request" - Should not matter

"requester_days_since_first_post_on_raop_at_retrieval"

## "requester_number_of_comments_at_request" - 

"requester_number_of_comments_at_retrieval"

## "requester_number_of_comments_in_raop_at_request"

"requester_number_of_comments_in_raop_at_retrieval"

## "requester_number_of_posts_at_request"

"requester_number_of_posts_at_retrieval" 

## "requester_number_of_posts_on_raop_at_request" 

"requester_number_of_posts_on_raop_at_retrieval"

## "requester_number_of_subreddits_at_request"

"requester_received_pizza"

## "requester_subreddits_at_request"

## "requester_upvotes_minus_downvotes_at_request"

"requester_upvotes_minus_downvotes_at_retrieval"

## "requester_upvotes_plus_downvotes_at_request"

"requester_upvotes_plus_downvotes_at_retrieval"

"requester_user_flair"

## "requester_username"

## "unix_timestamp_of_request"

## "unix_timestamp_of_request_utc"

## "giver_username_if_known"

### Thoughts

- Do univariate and bivariate analysis? OR correlation matrix
- Make word clouds for successful vs unsuccessful requests
- Got to see which factors are present in test data. Only 17 out of 32 are there
- Need to do analysis to see if account age, number of upvotes or downvotes, number of comments, number of subreddits make a difference or not
- Need to do NLP for the request text
- Request Time vs day of week is important
- Request Time vs hour of day
- For Feature Engineering, read the paper by Stanford and maybe that will be helpful
    - Topic Modeling
    - Stemming
    - Bag of Words
- For Model Selection, try
    - Naive Bayes
    - Regression
    - Random Forest
    - Neural Networks
- No need for at_retrieval stuff
- Talk about why we will use only columns present in both and disregard others
    - at_request over at_retrieval since that's more real-time
    - user_flair not required since this is after / we have received_pizza variable
    - post_was_edited / request_text - better one is edit_aware one
    - requester_received_pizza - to be predicted
