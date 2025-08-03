HC15T1: Handle Exceptions for File Reading and Velocity Calculation

```haskell
import System.IO
import System.IO.Error (catchIOError)
import Control.Exception (catch, SomeException)
import Text.Read (readMaybe)

-- Read distance from file
readDistance :: FilePath -> IO (Maybe Double)
readDistance path = catchIOError readFileSafe handler
  where
    readFileSafe = do
      content <- readFile path
      return $ readMaybe content
    handler e = do
      putStrLn $ "File error: " ++ show e
      return Nothing

-- Get time from user input
getTimeInput :: IO (Maybe Double)
getTimeInput = do
  putStrLn "Enter time (in seconds):"
  input <- getLine
  return $ readMaybe input

-- Calculate velocity
calculateVelocity :: Double -> Double -> Double
calculateVelocity distance time = distance / time

main :: IO ()
main = do
  putStrLn "Reading distance from 'distance.txt'..."
  mDistance <- readDistance "distance.txt"
  mTime     <- getTimeInput

  case (mDistance, mTime) of
    (Just d, Just t) | t /= 0 -> do
      let velocity = calculateVelocity d t
      putStrLn $ "Velocity is " ++ show velocity ++ " m/s"
    (Just _, Just 0) ->
      putStrLn "Time cannot be zero!"
    _ ->
      putStrLn "Failed to compute velocity due to invalid input."
```

---

### 📁 Additional Setup

Create a file named `distance.txt` with a number, like:

```
120.5
```

This represents the distance in meters.

---

### 🛠️ Run with Cabal

If you’re using a project structure with `app/Main.hs`, update the `.cabal` file to include:

```cabal
main-is:             Main.hs
hs-source-dirs:      app
build-depends:       base, text
default-language:    Haskell2010
```

Then from the project root:

```bash
cabal run
```
