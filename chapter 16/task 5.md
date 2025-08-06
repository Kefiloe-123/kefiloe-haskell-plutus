HC16T5: Uppercase String

```haskell
-- main.hs

-- Import the module needed for character case manipulation
import Data.Char (toUpper)

-- Define a function that converts all characters in a string to uppercase
toUpperCase :: String -> String
toUpperCase str = map toUpper str
-- 'map' applies the 'toUpper' function to each character in the string

-- Main function to test the toUpperCase function
main :: IO ()
main = do
    -- Define the input string
    let input = "Hello, Haskell!"

    -- Convert the string to uppercase
    let result = toUpperCase input

    -- Print the original and converted strings
    putStrLn ("Original: " ++ input)
    putStrLn ("Uppercase: " ++ result)
```

---

### 🛠️ How to Run:

Save it as `main.hs` and then:

```bash
runghc main.hs
```

Or compile:

```bash
ghc main.hs -o uppercaseApp
./uppercaseApp
```
