HC18T4: mapToBits Function

```haskell
-- main.hs

-- Function to convert a list of Booleans to a list of '1' and '0' characters using fmap
mapToBits :: [Bool] -> [Char]
mapToBits = fmap (\b -> if b then '1' else '0')
-- fmap applies the conversion function to each Bool in the list

-- Main function to demonstrate mapToBits
main :: IO ()
main = do
  let boolList = [True, False, True, True, False]
  let bitChars = mapToBits boolList

  putStrLn "Original Boolean List:"
  print boolList

  putStrLn "\nMapped to Bits:"
  print bitChars
```

---

### 💡 Explanation:

* `fmap (\b -> if b then '1' else '0')` maps each `True` to `'1'` and each `False` to `'0'`.
* Since lists are Functors, `fmap` works like `map`.

---

### 🛠️ How to Run:

Save the file as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o mapToBitsApp
./mapToBitsApp
```

---
