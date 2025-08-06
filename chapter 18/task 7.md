HC18T7: fmapTuple Function

```haskell
-- main.hs

-- fmapTuple applies a function to the second element of a tuple
-- using the Functor instance of (,) a
fmapTuple :: (b -> c) -> (a, b) -> (a, c)
fmapTuple = fmap
-- The (,) a type is a Functor in its second argument (b)
-- So fmap applies the function to the second element only

-- Example functions to apply
addExclamation :: String -> String
addExclamation s = s ++ "!"

double :: Int -> Int
double x = x * 2

-- Main function to demonstrate fmapTuple
main :: IO ()
main = do
  let pair1 = ("info", "hello")
  let pair2 = (10, 5)

  putStrLn "Applying addExclamation to second element of (\"info\", \"hello\"):"
  print (fmapTuple addExclamation pair1)

  putStrLn "Applying double to second element of (10, 5):"
  print (fmapTuple double pair2)
```

---

### 💡 Explanation:

* `(,) a` is a Functor over its **second** type parameter.
* So `fmap f (a, b)` will give `(a, f b)`
* `fmapTuple = fmap` works because `(a, _)` is already a Functor context

---

### 🧪 Example Output:

```
Applying addExclamation to second element of ("info", "hello"):
("info","hello!")
Applying double to second element of (10, 5):
(10,10)
```

---

### 🛠️ How to Run:

1. Save the code as `main.hs`
2. Run:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o fmapTupleApp
./fmapTupleApp
```

---
