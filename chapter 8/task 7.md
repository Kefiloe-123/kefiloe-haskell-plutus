HC8T7: Define a new type Animal using data with constructors Dog String and Cat String. Create a function describeAnimal :: Animal -> String that describes the animal. Create instances for a dog and a cat.

```haskell
-- Define the Animal data type
data Animal = Dog String | Cat String deriving Show

-- Function to describe the animal
describeAnimal :: Animal -> String
describeAnimal (Dog name) = "This is a dog named " ++ name ++ "."
describeAnimal (Cat name) = "This is a cat named " ++ name ++ "."

-- Create instances of a dog and a cat
myDog :: Animal
myDog = Dog "Buddy"

myCat :: Animal
myCat = Cat "Whiskers"

-- Example main to test the function
main :: IO ()
main = do
  putStrLn $ describeAnimal myDog
  putStrLn $ describeAnimal myCat
```

---

### ✅ Example Output:

```
This is a dog named Buddy.
This is a cat named Whiskers.
```

---

### ✔️ Explanation:

* `Animal` has two constructors: `Dog String` and `Cat String`, each holding the animal's name.
* `describeAnimal` uses **pattern matching** to return a description based on whether the animal is a dog or a cat.
* The example creates a dog named "Buddy" and a cat named "Whiskers".
