HC8T9: Record Type and Transaction Function

```haskell
-- Type synonyms for clarity
type Address = String
type Value = Int

-- Define the Transaction data type using record syntax
data Transaction = Transaction
  { from          :: Address
  , to            :: Address
  , amount        :: Value
  , transactionId :: String
  } deriving Show

-- Function to create a transaction and return the transaction ID
createTransaction :: Address -> Address -> Value -> String
createTransaction sender receiver val =
  let txId = sender ++ "->" ++ receiver ++ ":" ++ show val
      tx = Transaction { from = sender, to = receiver, amount = val, transactionId = txId }
  in transactionId tx

-- Example main to test the function
main :: IO ()
main = do
  let sender = "addr1"
      receiver = "addr2"
      value = 100
  let txId = createTransaction sender receiver value
  putStrLn $ "Created transaction with ID: " ++ txId
```

---

### ✅ Example Output:

```
Created transaction with ID: addr1->addr2:100
```

---

### ✔️ Explanation:

* `Transaction` is a record with four fields.
* `createTransaction` builds the `transactionId` from the input values and returns it.
* The actual `Transaction` is constructed inside the function (you can modify it to return the whole record if needed).
