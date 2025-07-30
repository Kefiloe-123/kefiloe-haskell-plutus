HC1T5 - Task 5: Laziness in Haskell

```haskell
-- main.hs
-- Define a custom Result type
data Result a = Success a | Error String
  deriving Show

-- Function to handle Result using pattern matching with '@'
handleResult :: Result Int -> String
handleResult res@(Success val)
  | val > 0   = "Positive result: " ++ show val ++ " from " ++ show res
  | val == 0  = "Zero result from: " ++ show res
  | otherwise = "Negative result: " ++ show val
handleResult err@(Error msg) = "Encountered error: " ++ msg ++ " from " ++ show err

main :: IO ()
main = do
  let results = [Success 42, Success 0, Success (-7), Error "Something went wrong"]
  mapM_ (putStrLn . handleResult) results
```

### 🔍 Highlights
- `Result a` is a generic type with two constructors: `Success a` and `Error String`.
- The `@` symbol is used to bind the entire constructor to a name (`res` or `err`) while still pattern matching on its contents.
- In `main`, it demonstrates handling different `Result Int` values.

You can run this with:
```
runhaskell main.hs
```
