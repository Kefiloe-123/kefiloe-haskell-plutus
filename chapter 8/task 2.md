HC8T2: Define a new type PaymentMethod with the constructors Cash, Card, and Cryptocurrency. Create a Person type that includes a name, address (tuple of String and Int), and a payment method. Create a person bob who pays with cash.

```haskell
-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency deriving Show

-- Define the Person data type
data Person = Person
  { name         :: String
  , address      :: (String, Int)  -- (Street, House Number)
  , paymentMethod :: PaymentMethod
  } deriving Show

-- Create a person named Bob who pays with Cash
bob :: Person
bob = Person
  { name = "Bob"
  , address = ("Main Street", 42)
  , paymentMethod = Cash
  }

-- Example main to print Bob's information
main :: IO ()
main = do
  putStrLn $ "Person: " ++ show bob
```

---

### ✅ Example Output:

```
Person: Person {name = "Bob", address = ("Main Street",42), paymentMethod = Cash}
```

---

### ✔️ Explanation:

* `PaymentMethod` is an enumeration with `Cash`, `Card`, and `Cryptocurrency`.
* `Person` is a **record syntax** type with fields: `name`, `address`, and `paymentMethod`.
* `address` is represented as a **tuple of `String` and `Int`**.
* The example creates a person called `bob` who lives at "Main Street 42" and pays with cash.
