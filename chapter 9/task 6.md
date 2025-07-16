HC9T6: Recursive Data Type for Tweets

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving Show

-- Example nested tweets (comments)
comment1 :: Tweet
comment1 = Tweet "Nice post!" 5 []

comment2 :: Tweet
comment2 = Tweet "Thanks for sharing!" 3 []

mainTweet :: Tweet
mainTweet = Tweet
  { content = "Just launched my new blog!"
  , likes = 100
  , comments = [comment1, comment2]
  }

-- Main function to print the tweet
main :: IO ()
main = do
  putStrLn "Main Tweet:"
  print mainTweet
```

---

### ✅ Example Output (simplified):

```
Main Tweet:
Tweet {content = "Just launched my new blog!", likes = 100, comments = [Tweet {content = "Nice post!", likes = 5, comments = []},Tweet {content = "Thanks for sharing!", likes = 3, comments = []}]}
```

---

### ✔️ Explanation:

* The data type is **recursive** because `comments :: [Tweet]` allows a tweet to contain replies, which are also tweets.
* This mimics real-world nested conversations.
* `deriving Show` allows printing the tweet structure directly.
