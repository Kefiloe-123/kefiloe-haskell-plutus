HC8T8: Type Synonyms and Greeting Function

```haskell
-- Type synonyms
type Name = String
type Age = Int

-- Function to generate a greeting
greet :: Name -> Age -> String
greet name age = "Hello, " ++ name ++ "! You are " ++ show age ++ " years old."

-- Example main to test the function
main :: IO ()
main = do
  putStrLn $ greet "Alice" 25
  putStrLn $ greet "Bob" 30
```

---

### ✅ Example Output:

```
Hello, Alice! You are 25 years old.
Hello, Bob! You are 30 years old.
```

---

### ✔️ Explanation:

* `type Name = String` and `type Age = Int` are type synonyms to improve code clarity.
* `greet` takes a `Name` and an `Age`, and returns a formatted greeting.
* In `main`, the function is tested with example names and ages.

