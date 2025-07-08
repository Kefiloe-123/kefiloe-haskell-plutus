HC5T6: Function Composition

```haskell
-- Define the function using composition
evenSquares :: [Int] -> [Int]
evenSquares = filter even . map (^2)

-- Main function to test evenSquares
main :: IO ()
main = do
    print (evenSquares [1,2,3,4,5])    -- Output: [4,16]
    print (evenSquares [6,7,8])        -- Output: [36,64]
    print (evenSquares [])              -- Output: []
```

---

### Explanation:

* `map (^2)` squares each number in the list.
* `filter even` keeps only even numbers.
* Using composition (`.`), we combine them as `filter even . map (^2)`, meaning: first square all, then filter even.

---

### Output:

```
[4,16]
[36,64]
[]
```
