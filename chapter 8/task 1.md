HC8T1: Create a type synonym called Address for String and a type synonym called Value for Int. Define a function generateTx :: Address -> Address -> Value -> String that takes two addresses and a value and returns a string concatenating these.

```haskell
-- Type synonyms
type Address = String
type Value = Int

-- Function to generate a transaction description
generateTx :: Address -> Address -> Value -> String
generateTx fromAddr toAddr amount =
  "Transaction from " ++ fromAddr ++ " to " ++ toAddr ++ " of value " ++ show amount

-- Example main to test the function
main :: IO ()
main = do
  let sender = "addr1qxy"
      receiver = "addr1abcd"
      amount = 100

  putStrLn $ generateTx sender receiver amount
```

---

### ✅ Example Output:

```
Transaction from addr1qxy to addr1abcd of value 100
```

---

### ✔️ Explanation:

* `type Address = String`: creates a type synonym for clarity, but at runtime it's still a `String`.
* `type Value = Int`: same for `Value`.
* `generateTx`: concatenates the two addresses and the value into a descriptive string.
