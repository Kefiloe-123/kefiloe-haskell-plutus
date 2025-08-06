HC18T8: identityLawCheck Function

```haskell
-- main.hs

-- identityLawCheck checks the Functor identity law: fmap id == id
-- It takes a Functor value and compares fmap id with the value itself
identityLawCheck :: (Eq (f a), Functor f) => f a -> Bool
identityLawCheck x = fmap id x == x

-- Main function to test the identity law with Maybe and List functors
main :: IO ()
main = do
  putStrLn "Testing Functor identity law..."

  -- Test with Maybe
  let justVal = Just 42
  let nothingVal = Nothing :: Maybe Int

  putStrLn $ "Just 42 satisfies identity law: " ++ show (identityLawCheck justVal)
  putStrLn $ "Nothing satisfies identity law: " ++ show (identityLawCheck nothingVal)

  -- Test with List
  let listVal = [1, 2, 3]
  let emptyList = [] :: [Int]

  putStrLn $ "[1,2,3] satisfies identity law: " ++ show (identityLawCheck listVal)
  putStrLn $ "[] satisfies identity law: " ++ show (identityLawCheck emptyList)
```

---

### 💡 Explanation:

* `identityLawCheck` takes any functor `f a`, and verifies `fmap id x == x`
* Works with any Functor that has an `Eq` instance (like `Maybe`, `[]`, etc.)

---

### 🧪 Sample Output:

```
Testing Functor identity law...
Just 42 satisfies identity law: True
Nothing satisfies identity law: True
[1,2,3] satisfies identity law: True
[] satisfies identity law: True
```

---

### 🛠️ How to Run:

Save the file as `main.hs` and then:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o identityLawCheckApp
./identityLawCheckApp
```

---
