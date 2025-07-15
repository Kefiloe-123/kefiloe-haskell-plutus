HC9T1: Define a Parametric Type Synonym


```haskell
-- Define a parametric type synonym Entity
type Entity a = (String, a)
-- This means: an Entity consists of a name (String) and an address of type 'a'

-- Example usage with String address
personEntity :: Entity String
personEntity = ("Alice", "123 Main St")

-- Example usage with (String, Int) as address (e.g., street name and number)
businessEntity :: Entity (String, Int)
businessEntity = ("Coffee Shop", ("Market St", 42))

-- Main to print both entities
main :: IO ()
main = do
  putStrLn "Person Entity:"
  print personEntity

  putStrLn "\nBusiness Entity:"
  print businessEntity
```

---

### ✅ Example Output:

```
Person Entity:
("Alice","123 Main St")

Business Entity:
("Coffee Shop",("Market St",42))
```

---

### ✔️ Explanation:

* `type Entity a = (String, a)` defines a **type synonym** where the first element is the entity's name, and the second is a generic address of type `a`.
* This allows `Entity` to be reused flexibly with different address formats.
