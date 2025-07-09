HC8T4: Define a new type Employee using record syntax with fields name :: String and experienceInYears :: Float. Create an employee richard with 7.5 years of experience.


```haskell
-- Define the Employee type using record syntax
data Employee = Employee
  { name :: String
  , experienceInYears :: Float
  } deriving Show

-- Create an employee named Richard with 7.5 years of experience
richard :: Employee
richard = Employee
  { name = "Richard"
  , experienceInYears = 7.5
  }

-- Example main to print Richard's information
main :: IO ()
main = do
  putStrLn $ "Employee Name: " ++ name richard
  putStrLn $ "Experience (years): " ++ show (experienceInYears richard)
```

---

### ✅ Example Output:

```
Employee Name: Richard
Experience (years): 7.5
```

---

### ✔️ Explanation:

* `Employee` is defined using **record syntax** with two fields: `name` and `experienceInYears`.
* `deriving Show` allows the whole record to be printed if desired.
* The `richard` instance initializes the fields.
* In `main`, it accesses the fields using the generated field accessors.
