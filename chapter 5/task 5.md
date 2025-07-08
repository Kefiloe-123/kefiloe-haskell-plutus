HC5T5: Partial Application

```haskell
-- Define multiplyByFive using partial application
multiplyByFive :: Num a => a -> a
multiplyByFive = (5 *)

-- Main function to test multiplyByFive
main :: IO ()
main = do
    print (multiplyByFive 3)    -- Output: 15
    print (multiplyByFive 10)   -- Output: 50
    print (multiplyByFive 0)    -- Output: 0
```

---

### Explanation:

* `(5 *)` is a partially applied multiplication function where 5 is fixed as the first operand.
* So, `multiplyByFive x` is equivalent to `5 * x`.

---

### Output:

```
15
50
0
