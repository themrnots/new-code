import os
import sys
import tweepy

# Check for required environment variables
required_secrets = ["X_API_KEY", "X_API_SECRET", "X_ACCESS_TOKEN", "X_ACCESS_TOKEN_SECRET"]
if not all(secret in os.environ for secret in required_secrets):
    print("Error: Missing one or more API keys in GitHub Secrets!")
    sys.exit(1)

# Initialize Tweepy Client (API v2)
client = tweepy.Client(
    consumer_key=os.environ["X_API_KEY"],
    consumer_secret=os.environ["X_API_SECRET"],
    access_token=os.environ["X_ACCESS_TOKEN"],
    access_token_secret=os.environ["X_ACCESS_TOKEN_SECRET"]
)

tweet_text = "gm ☀️"

try:
    # Send tweet
    response = client.create_tweet(text=tweet_text)
    tweet_id = response.data['id']
    print(f"Tweet sent successfully! Tweet ID: {tweet_id}")
    
except tweepy.TweepyException as e:
    print(f"Twitter API Error: {e}")
except Exception as e:
    print(f"Unexpected Error: {e}")
