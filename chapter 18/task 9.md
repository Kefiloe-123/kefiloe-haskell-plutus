HC18T9: compositionLawCheck Function

```haskell
-- main.hs

-- compositionLawCheck checks the Functor composition law:
-- fmap (f . g) x == (fmap f . fmap g) x
compositionLawCheck :: (Eq (f c), Functor f) => (b -> c) -> (a -> b) -> f a -> Bool
compositionLawCheck f g x = fmap (f . g) x == (fmap f . fmap g) x

-- Example functions to use in composition
add1 :: Int -> Int
add1 x = x + 1

double :: Int -> Int
double x = x * 2

toUpperChar :: Char -> Char
toUpperChar c = if c >= 'a' && c <= 'z' then toEnum (fromEnum c - 32) else c

exclaim :: Char -> String
exclaim c = [c] ++ "!"

-- Main function to run composition checks
main :: IO ()
main = do
  putStrLn "Testing Functor composition law..."

  -- Test with Maybe Int
  let justVal = Just 3
  let nothingVal = Nothing :: Maybe Int

  putStrLn $ "Just 3 satisfies composition law: " ++ show (compositionLawCheck add1 double justVal)
  putStrLn $ "Nothing satisfies composition law: " ++ show (compositionLawCheck add1 double nothingVal)

  -- Test with List Int
  let listVal = [1, 2, 3]
  let emptyList = [] :: [Int]

  putStrLn $ "[1,2,3] satisfies composition law: " ++ show (compositionLawCheck add1 double listVal)
  putStrLn $ "[] satisfies composition law: " ++ show (compositionLawCheck add1 double emptyList)

  -- Test with List Char
  let charList = ['a', 'b']
  putStrLn $ "['a','b'] with Char -> String satisfies composition law: " ++
    show (compositionLawCheck exclaim toUpperChar charList)
```

---

### 🧪 Example Output

```
Testing Functor composition law...
Just 3 satisfies composition law: True
Nothing satisfies composition law: True
[1,2,3] satisfies composition law: True
[] satisfies composition law: True
['a','b'] with Char -> String satisfies composition law: True
```

---

### 🛠️ How to Run:

Save it as `main.hs`, then run it with:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o functorCheck
./functorCheck
```

---
