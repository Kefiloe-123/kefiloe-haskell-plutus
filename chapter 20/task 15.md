HC20T15: treeSum with Custom Monad

```haskell
-- main.hs
-- This program defines a binary tree and uses a custom monad to sum its elements.

-- Define a simple binary tree data structure
data Tree a = Empty
            | Node a (Tree a) (Tree a)
            deriving (Show)

-- A custom monad to encapsulate computations over Tree
newtype TreeMonad a = TreeMonad { runTreeMonad :: a }

-- Make TreeMonad an instance of Functor
instance Functor TreeMonad where
    fmap f (TreeMonad x) = TreeMonad (f x)

-- Make TreeMonad an instance of Applicative
instance Applicative TreeMonad where
    pure = TreeMonad
    (TreeMonad f) <*> (TreeMonad x) = TreeMonad (f x)

-- Make TreeMonad an instance of Monad
instance Monad TreeMonad where
    return = pure
    (TreeMonad x) >>= f = f x

-- Function to sum all elements in a binary tree using TreeMonad
treeSum :: Tree Int -> TreeMonad Int
treeSum Empty = return 0
treeSum (Node val left right) = do
    leftSum <- treeSum left
    rightSum <- treeSum right
    return (val + leftSum + rightSum)

-- Sample tree:
--       5
--      / \
--     3   7
--    / \
--   1   4

sampleTree :: Tree Int
sampleTree = Node 5
                (Node 3
                    (Node 1 Empty Empty)
                    (Node 4 Empty Empty))
                (Node 7 Empty Empty)

-- Main function
main :: IO ()
main = do
    let total = runTreeMonad (treeSum sampleTree)
    putStrLn $ "Sum of tree elements: " ++ show total
```

---

### 🧪 Output:

```
Sum of tree elements: 20
```

---

### 🔍 Summary:

* The `TreeMonad` is a **simple wrapper** to show how you can build monadic logic for traversing data structures.
* You could extend this to add **logging**, **state tracking**, or **error handling** using other monad transformers.
