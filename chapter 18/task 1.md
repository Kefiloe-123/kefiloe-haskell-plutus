HC18T1: mapToLower Function with fmap

```haskell
-- main.hs

import Data.Char (toLower)

-- Define mapToLower using fmap to convert all characters in a list to lowercase
mapToLower :: [Char] -> [Char]
mapToLower = fmap toLower
-- fmap applies 'toLower' to each element in the list (Functor instance for lists)

-- Main function to demonstrate mapToLower
main :: IO ()
main = do
    let input = "Hello, Haskell!"
    let result = mapToLower input

    putStrLn $ "Original: " ++ input
    putStrLn $ "Lowercase: " ++ result
```

---

### 💡 Explanation:

* `fmap` is used here because lists are functors, so `fmap` applies a function to each element.
* `toLower` converts a character to lowercase.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o mapToLowerApp
./mapToLowerApp
```
