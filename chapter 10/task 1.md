HC10T1: ShowSimple Type Class

```haskell
-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency
  deriving Show

-- Define the ShowSimple type class
class ShowSimple a where
  showSimple :: a -> String

-- Implement ShowSimple instance for PaymentMethod
instance ShowSimple PaymentMethod where
  showSimple Cash           = "Paid with cash"
  showSimple Card           = "Paid with card"
  showSimple Cryptocurrency = "Paid with cryptocurrency"

-- Main function to demonstrate showSimple
main :: IO ()
main = do
  putStrLn $ showSimple Cash
  putStrLn $ showSimple Card
  putStrLn $ showSimple Cryptocurrency
```

---

### ✅ Example Output:

```
Paid with cash
Paid with card
Paid with cryptocurrency
```

---

### ✔️ Explanation:

* `ShowSimple` is a **custom alternative** to the built-in `Show` class.
* You can define simpler or more domain-specific string representations.
* This setup is ideal for formatting output without relying on derived `Show`.
