HC8T5: Define a type Person using a record syntax that includes name :: String, age :: Int, and isEmployed :: Bool. Create a person1 who is employed, and a person2 who is unemployed.

```haskell
-- Define the Person type using record syntax
data Person = Person
  { name       :: String
  , age        :: Int
  , isEmployed :: Bool
  } deriving Show

-- Create person1 who is employed
person1 :: Person
person1 = Person
  { name = "Alice"
  , age = 30
  , isEmployed = True
  }

-- Create person2 who is unemployed
person2 :: Person
person2 = Person
  { name = "Bob"
  , age = 25
  , isEmployed = False
  }

-- Example main to print their information
main :: IO ()
main = do
  putStrLn $ "Person 1: " ++ show person1
  putStrLn $ "Person 2: " ++ show person2
```

---

### ✅ Example Output:

```
Person 1: Person {name = "Alice", age = 30, isEmployed = True}
Person 2: Person {name = "Bob", age = 25, isEmployed = False}
```

---

### ✔️ Explanation:

* `Person` is defined using **record syntax** with fields for `name`, `age`, and `isEmployed`.
* Two persons are created:

  * `person1`: named Alice, age 30, employed.
  * `person2`: named Bob, age 25, unemployed.
* The `Show` instance is derived to allow easy printing.
