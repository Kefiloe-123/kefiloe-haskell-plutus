HC19T8: discardSecond with <*

```haskell
-- main.hs

import Control.Applicative ((<*))

-- discardSecond runs two Applicative actions, returns the result of the first,
-- discarding the second using the <* operator
discardSecond :: Applicative f => f a -> f b -> f a
discardSecond = (<*)

-- Main function demonstrating discardSecond with IO actions
main :: IO ()
main = do
  let action1 = putStrLn "First action" >> pure 42
  let action2 = putStrLn "Second action" >> pure "ignored"

  putStrLn "Running discardSecond (action1 <* action2):"
  result <- discardSecond action1 action2
  putStrLn $ "Result (from first action): " ++ show result
```

---

### 💡 Explanation:

* `<*` sequences two Applicative actions.
* It runs the **first** action, then the **second**, but returns the **result of the first**.
* Useful when you want to run some side effects but keep only the first result.

---

### 🛠️ How to Run:

Save as `main.hs`, then run:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o discardSecondApp
./discardSecondApp
```

---
