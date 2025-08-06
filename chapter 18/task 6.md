HC18T6: applyToMaybe Function

```haskell
-- main.hs

-- applyToMaybe uses fmap to apply a function to the value inside a Maybe
applyToMaybe :: (a -> b) -> Maybe a -> Maybe b
applyToMaybe = fmap
-- fmap applies the function if the Maybe is Just x, otherwise it returns Nothing

-- Example functions to apply
square :: Int -> Int
square x = x * x

toUppercase :: Char -> Char
toUppercase c = if c >= 'a' && c <= 'z' then toEnum (fromEnum c - 32) else c

-- Main function to demonstrate applyToMaybe
main :: IO ()
main = do
  -- Example with Int
  let num = Just 5
  let nothingNum = Nothing :: Maybe Int

  putStrLn "Applying square to Just 5:"
  print (applyToMaybe square num)

  putStrLn "Applying square to Nothing:"
  print (applyToMaybe square nothingNum)

  -- Example with Char
  let char = Just 'b'
  let nothingChar = Nothing :: Maybe Char

  putStrLn "Applying toUppercase to Just 'b':"
  print (applyToMaybe toUppercase char)

  putStrLn "Applying toUppercase to Nothing:"
  print (applyToMaybe toUppercase nothingChar)
```

---

### 💡 Output Explanation:

When run, the output would look like:

```
Applying square to Just 5:
Just 25
Applying square to Nothing:
Nothing
Applying toUppercase to Just 'b':
Just 'B'
Applying toUppercase to Nothing:
Nothing
```

---

### 🛠️ How to Run:

1. Save the code to a file named `main.hs`
2. Run with:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o maybeApp
./maybeApp
```

---
