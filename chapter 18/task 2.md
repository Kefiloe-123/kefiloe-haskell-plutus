HC18T2: Functor Instance for Tree

```haskell
-- main.hs

-- Define a binary tree data type
data Tree a
  = Empty
  | Node a (Tree a) (Tree a)
  deriving (Show, Eq)

-- Create a Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty                                     -- Nothing to map in an empty tree
  fmap f (Node x left right) =                             -- Apply f to the value at the node
    Node (f x) (fmap f left) (fmap f right)                -- Recursively map over left and right subtrees

-- Helper function to build a sample tree
sampleTree :: Tree Int
sampleTree =
  Node 1
    (Node 2 Empty Empty)
    (Node 3
      (Node 4 Empty Empty)
      Empty)

-- Main function to demonstrate fmap over Tree
main :: IO ()
main = do
  putStrLn "Original Tree:"
  print sampleTree

  let incrementedTree = fmap (+1) sampleTree
  putStrLn "\nTree after fmap (+1):"
  print incrementedTree

  let doubledTree = fmap (*2) sampleTree
  putStrLn "\nTree after fmap (*2):"
  print doubledTree
```

---

### 💡 Explanation:

* The `Tree` type has two constructors:

  * `Empty`: an empty tree.
  * `Node a left right`: a node containing a value and two subtrees.
* The `Functor` instance uses `fmap` to:

  * Leave `Empty` unchanged.
  * Apply a function `f` to the node's value and recurse on its children.
* `main` builds a sample tree and shows how to use `fmap` with it.

---

### 🛠️ How to Run:

Save as `main.hs`, then run with:

```bash
runghc main.hs
```

Or compile and run:

```bash
ghc main.hs -o treeFunctorApp
./treeFunctorApp
```
