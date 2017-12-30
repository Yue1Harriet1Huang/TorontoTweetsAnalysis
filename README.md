# Analyze Tweets in the Toronto Area

1. Scrape tweets with the keyword 'toronto'
---

```
!pip install tweepy==3.3.0
```

```
import tweepy
from tweepy import OAuthHandler
 
consumer_key = '7LaZr3GMUpeZGfeldeRRyhf4g'
consumer_secret = 'j28Qn4bzfLTAaURVbo8myyabBR60CSJ9hnuf1KkRKpKl5C30M3'
access_token = '55717701-rkG9z0elwMusFlgbSFomLVXIAzcYMUTrn5BCPwM3l'
access_secret = 'L5hicGOH8ewvaerUA8spfJEOrQmL4yD8mBeW77NqXM1i8'
 
auth = OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_secret)
 
api = tweepy.API(auth)
```

```
for status in tweepy.Cursor(api.home_timeline).items(10):
    # Process a single status
    print(status.text)
```

```
#tweepy.Cursor(api.search, q='cricket', geocode="43.6532,-79.3832,1km").items(10)

cursor = tweepy.Cursor(api.search, q='toronto').items(10)

for tweet in cursor:
   print(tweet.created_at, tweet.text, tweet.lang)
```

