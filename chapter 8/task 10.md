HC8T10: Deriving Show for Book

```haskell
-- Define the Book type with Show deriving
data Book = Book
  { title  :: String
  , author :: String
  , year   :: Int
  } deriving Show

-- Example book instance
myBook :: Book
myBook = Book
  { title  = "The Hobbit"
  , author = "J.R.R. Tolkien"
  , year   = 1937
  }

-- Main function to print the book
main :: IO ()
main = do
  putStrLn "Book info:"
  print myBook
```

---

### ✅ Example Output:

```
Book info:
Book {title = "The Hobbit", author = "J.R.R. Tolkien", year = 1937}
```

---

### ✔️ Explanation:

* The `Book` type is defined with three fields: `title`, `author`, and `year`.
* `deriving Show` automatically creates an instance so the book can be printed using `print`.
* `myBook` is an example instance with sample data.
