HC9T10: Binary Search Tree Data Type

```haskell
-- Define the binary search tree data type
data BST a = Empty
           | Node a (BST a) (BST a)
           deriving Show

-- Example BST manually constructed
exampleBST :: BST Int
exampleBST =
  Node 10
    (Node 5
      (Node 2 Empty Empty)
      (Node 7 Empty Empty))
    (Node 15
      (Node 12 Empty Empty)
      (Node 20 Empty Empty))

-- Main function to print the BST
main :: IO ()
main = do
  putStrLn "Example BST structure:"
  print exampleBST
```

---

### ✅ Example Output:

```
Example BST structure:
Node 10 (Node 5 (Node 2 Empty Empty) (Node 7 Empty Empty)) (Node 15 (Node 12 Empty Empty) (Node 20 Empty Empty))
```

---

### ✔️ Explanation:

* The `BST a` data type is **recursive and parametric**:

  * `Empty`: represents an empty tree.
  * `Node a left right`: stores a value of type `a`, and two subtrees.
* The example builds a binary search tree with integer values.

---
