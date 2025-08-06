HC20T5: Reader Monad for Configurable Greeting

```haskell
-- main.hs

-- Import Reader monad
import Control.Monad.Reader

-- Define a configuration data type
data Config = Config
  { greetingPrefix :: String
  , punctuation    :: String
  }

-- Define a type alias for our Reader monad with Config
type AppReader = Reader Config

-- Function that creates a greeting for a given user using the configuration
greetUser :: String -> AppReader String
greetUser name = do
  config <- ask  -- Get the configuration from the Reader context
  let prefix = greetingPrefix config
      punct  = punctuation config
  return $ prefix ++ ", " ++ name ++ punct

-- Run the Reader monad with a given config and list of users
main :: IO ()
main = do
  let config = Config "Welcome" "!"
      users  = ["Alice", "Bob", "Charlie"]
      greetings = map (\name -> runReader (greetUser name) config) users
  putStrLn "Generated Greetings:"
  mapM_ putStrLn greetings
```

---

### 💡 Explanation:

* **`Config`**: Holds customizable settings.
* **`greetUser`**: Fetches configuration using `ask` from the Reader monad and builds a greeting.
* **`runReader`**: Applies the `Config` to the `greetUser` function.
* **`main`**: Creates a sample `Config` and greets a list of users.

---

### 🛠️ How to Run:

Save as `main.hs` and run:

```bash
runghc main.hs
```
