HC19T1: Applicative Instance for Pair

```haskell
-- main.hs

-- Define a simple Pair data type holding two values of the same type
data Pair a = Pair a a deriving (Show)

-- Functor instance for Pair
instance Functor Pair where
  fmap f (Pair x y) = Pair (f x) (f y)
  -- fmap applies the function f to both elements of the pair

-- Applicative instance for Pair
instance Applicative Pair where
  pure x = Pair x x
  -- pure replicates the value x in both positions

  (Pair f g) <*> (Pair x y) = Pair (f x) (g y)
  -- <*> applies the first function to the first value and the second function to the second value

-- Main function to demonstrate the Pair Applicative
main :: IO ()
main = do
  let pf = Pair (+1) (*2)     -- Pair of functions
  let pv = Pair 10 5          -- Pair of values

  let result = pf <*> pv      -- Apply the functions to the values

  putStrLn "Applying Pair (+1, *2) to Pair (10, 5):"
  print result                -- Expected output: Pair 11 10
```

---

### 💡 Explanation:

* `data Pair a = Pair a a`: defines a type that holds two values of the same type.
* The `Functor` instance applies a function to both values in the pair.
* The `Applicative` instance:

  * `pure x` gives `Pair x x`.
  * `(Pair f g) <*> (Pair x y)` applies `f` to `x` and `g` to `y`.

---

### 🛠️ How to Run:

Save this as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o pairApp
./pairApp
```

---
