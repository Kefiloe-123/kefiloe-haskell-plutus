HC12T2: Add Two Numbers

```haskell
-- This program defines a function addTwoNumbers that takes two integers and returns their sum.
-- It reads two integers from the user, adds them, and prints the result.

-- Define the function
addTwoNumbers :: Int -> Int -> Int
addTwoNumbers x y = x + y

-- Main function
main :: IO ()
main = do
    -- Ask the user for the first number
    putStrLn "Enter the first number:"
    input1 <- getLine

    -- Ask the user for the second number
    putStrLn "Enter the second number:"
    input2 <- getLine

    -- Convert input strings to integers
    let num1 = read input1 :: Int
    let num2 = read input2 :: Int

    -- Call the function and store the result
    let sumResult = addTwoNumbers num1 num2

    -- Print the result
    putStrLn ("The sum is: " ++ show sumResult)
```

### ✅ To Run:

* **In an online Haskell editor**: Just paste the whole code and click **Run**.
* **Locally with GHC**:

  1. Save as `Main.hs`
  2. In terminal:

     ```bash
     ghc Main.hs
     ./Main
     ```

### 💬 Example:

```
Enter the first number:
10
Enter the second number:
15
The sum is: 25
```
