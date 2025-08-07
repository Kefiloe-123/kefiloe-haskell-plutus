HC20T14: mapMFilter Monadic Map-Filter

```haskell
-- main.hs
-- This program defines a monadic map + filter function called mapMFilter.
-- It demonstrates how to use this function with the Maybe monad.

import Control.Monad (forM)

-- | mapMFilter applies a monadic function to a list,
-- returning only the 'Just' results (i.e., it filters out 'Nothing')
mapMFilter :: Monad m => (a -> m (Maybe b)) -> [a] -> m [b]
mapMFilter f xs = do
    results <- mapM f xs           -- Apply the function to all elements
    return [y | Just y <- results] -- Filter out Nothings and unwrap Just values

-- Example monadic function: keep even numbers and double them
processNumber :: Int -> Maybe (Maybe Int)
processNumber x = return $
    if even x then Just (x * 2) else Nothing

-- Main function to test mapMFilter
main :: IO ()
main = do
    let numbers = [1..10]
    let result = mapMFilter processNumber numbers
    case result of
        Just doubledEvens -> putStrLn $ "Processed evens: " ++ show doubledEvens
        Nothing -> putStrLn "Something went wrong."
```

---

### 🔍 How it works:

* **`mapMFilter`**: takes a function that returns `m (Maybe b)` and returns only the `Just` results.
* In the example, we use it with **`Maybe`** to filter out odd numbers and double the even ones.
* It mimics a **combined `mapM` + filter operation**.

---

### 🧪 Output:

```
Processed evens: [4,8,12,16,20]
```


