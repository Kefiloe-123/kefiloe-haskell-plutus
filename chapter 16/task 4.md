HC16T4: Filter Even Numbers

```haskell
-- main.hs

-- Define a function to filter only even numbers from a list
filterEvens :: [Int] -> [Int]
filterEvens xs = filter even xs
-- 'filter' is a standard Haskell function that keeps elements satisfying a condition
-- 'even' is a built-in function that returns True for even numbers

-- Main function to test the filterEvens function
main :: IO ()
main = do
    -- Define a list of integers
    let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    
    -- Apply the filterEvens function
    let evens = filterEvens numbers

    -- Print the original and filtered lists
    putStrLn ("Original list: " ++ show numbers)
    putStrLn ("Even numbers: " ++ show evens)
```

---

### 🛠️ How to Run:

Save this as `main.hs`, then run it with:

```bash
runghc main.hs
```

Or compile it:

```bash
ghc main.hs -o evenFilter
./evenFilter
```
