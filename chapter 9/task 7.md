HC9T7: Engagement Function for Tweets

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving Show

-- Recursive function to calculate total engagement
engagement :: Tweet -> Int
engagement (Tweet _ likes comments) =
  likes + sum (map engagement comments)

-- Example tweets
comment1 :: Tweet
comment1 = Tweet "Nice!" 3 []

comment2 :: Tweet
comment2 = Tweet "Thanks for sharing." 2 []

nestedComment :: Tweet
nestedComment = Tweet "I agree!" 1 [comment2]

mainTweet :: Tweet
mainTweet = Tweet
  { content = "Check out my new blog post!"
  , likes = 10
  , comments = [comment1, nestedComment]
  }

-- Main to test engagement
main :: IO ()
main = do
  putStrLn "Total engagement of main tweet:"
  print (engagement mainTweet)
```

---

### ✅ Example Output:

```
Total engagement of main tweet:
16
```

---

### ✔️ Engagement Calculation Explained:

* `mainTweet` has 10 likes
* `comment1` has 3 likes
* `nestedComment` has 1 like, and its sub-comment (`comment2`) has 2 likes
* Total: `10 + 3 + 1 + 2 = 16`

---
