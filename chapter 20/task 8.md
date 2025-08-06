HC20T8: Parser Monad for Simple Expressions

```haskell
-- main.hs
-- A simple expression parser using the Parser monad.
-- Supports + and * with proper precedence.

import Control.Applicative
import Data.Char

-- Define the Parser type
newtype Parser a = Parser { runParser :: String -> [(a, String)] }

-- Make Parser a Functor
instance Functor Parser where
  fmap f p = Parser $ \input -> 
    [(f a, rest) | (a, rest) <- runParser p input]

-- Make Parser an Applicative
instance Applicative Parser where
  pure a = Parser $ \input -> [(a, input)]
  pf <*> pa = Parser $ \input -> 
    [(f a, rest2) | (f, rest1) <- runParser pf input,
                    (a, rest2) <- runParser pa rest1]

-- Make Parser an Alternative
instance Alternative Parser where
  empty = Parser $ const []
  p1 <|> p2 = Parser $ \input -> 
    case runParser p1 input of
      [] -> runParser p2 input
      res -> res

-- Make Parser a Monad
instance Monad Parser where
  return = pure
  p >>= f = Parser $ \input ->
    concat [runParser (f a) rest | (a, rest) <- runParser p input]

-- Basic parsers
item :: Parser Char
item = Parser $ \input -> 
  case input of
    [] -> []
    (x:xs) -> [(x, xs)]

-- Parser that satisfies a predicate
satisfy :: (Char -> Bool) -> Parser Char
satisfy pred = do
  c <- item
  if pred c then return c else empty

-- Parse a specific character
char :: Char -> Parser Char
char c = satisfy (== c)

-- Parse a digit character
digit :: Parser Char
digit = satisfy isDigit

-- Parse a number (e.g., "123") into an Int
number :: Parser Int
number = do
  digits <- some digit
  return (read digits)

-- Skip spaces
spaces :: Parser ()
spaces = many (satisfy isSpace) >> return ()

-- Token parser: skips trailing spaces
token :: Parser a -> Parser a
token p = spaces >> p

symbol :: Char -> Parser Char
symbol c = token (char c)

-- Recursive expression grammar:
-- expr   ::= term ('+' expr | ε)
-- term   ::= factor ('*' term | ε)
-- factor ::= number | '(' expr ')'

-- Parse a factor: a number or parenthesized expression
factor :: Parser Int
factor = token number <|> do
  symbol '('
  x <- expr
  symbol ')'
  return x

-- Parse a term: factor * factor * ...
term :: Parser Int
term = do
  f <- factor
  rest f
  where
    rest acc = (do
        symbol '*'
        f2 <- factor
        rest (acc * f2)) <|> return acc

-- Parse an expression: term + term + ...
expr :: Parser Int
expr = do
  t <- term
  rest t
  where
    rest acc = (do
        symbol '+'
        t2 <- term
        rest (acc + t2)) <|> return acc

-- Main entry function to run parser
parseExpr :: String -> Either String Int
parseExpr input =
  case runParser expr input of
    [(result, "")] -> Right result
    [(_, leftover)] -> Left ("Unconsumed input: " ++ leftover)
    [] -> Left "Parse error"

-- Main function with tests
main :: IO ()
main = do
  let examples = ["2+3", "4+5*6", "(1+2)*3", "7*(2+3)", "10+20*3+1"]
  mapM_ (\ex -> putStrLn $ ex ++ " = " ++ show (parseExpr ex)) examples
```

---

### 💡 Example Output

```haskell
2+3 = Right 5
4+5*6 = Right 34
(1+2)*3 = Right 9
7*(2+3) = Right 35
10+20*3+1 = Right 71
```

---

### 🧠 What’s Happening

* We manually define a **Parser monad** with `Functor`, `Applicative`, `Monad`, and `Alternative` instances.
* The parser supports:

  * Integer numbers
  * Addition `+`
  * Multiplication `*`
  * Parentheses `(...)` with correct precedence
* `expr` handles addition.
* `term` handles multiplication.
* `factor` handles numbers and nested expressions.

---

### 🛠️ How to Run

Save this as `main.hs`, then run:

```bash
runghc main.hs
```

or

```bash
ghc main.hs -o parserApp
./parserApp
```

---
