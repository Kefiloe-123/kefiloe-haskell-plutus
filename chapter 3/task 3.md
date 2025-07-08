HC3T3 - Task 3: Convert an RGB color to a hex string using let bindings

```haskell
import Text.Printf (printf)

-- Function to convert RGB (Int, Int, Int) to Hex String
rgbToHex :: (Int, Int, Int) -> String
rgbToHex (r, g, b) =
    let redHex   = printf "%02X" r
        greenHex = printf "%02X" g
        blueHex  = printf "%02X" b
    in redHex ++ greenHex ++ blueHex

-- Main function to test rgbToHex
main :: IO ()
main = do
    putStrLn ("rgbToHex (255, 0, 127): " ++ rgbToHex (255, 0, 127))  -- Expected: "FF007F"
    putStrLn ("rgbToHex (0, 255, 64): " ++ rgbToHex (0, 255, 64))   -- Expected: "00FF40"
```

---

### ▶ **Example Output:**

```
rgbToHex (255, 0, 127): FF007F
rgbToHex (0, 255, 64): 00FF40
```

---

### 🔍 **Explanation:**

| RGB Tuple       | Hex String |
| --------------- | ---------- |
| `(255, 0, 127)` | `"FF007F"` |
| `(0, 255, 64)`  | `"00FF40"` |

* `printf "%02X"` converts an `Int` to a two-character uppercase hexadecimal string.
* **`let` bindings** are used to assign intermediate results (`redHex`, `greenHex`, `blueHex`).
* The three hex strings are concatenated with `++`.

---

### ✔ **How to Run:**

1. Save this as `RGBToHex.hs`.
2. Compile it with the `Text.Printf` library (built-in):

   ```bash
   ghc RGBToHex.hs
   ```
3. Run:

   ```bash
   ./RGBToHex
   ```

---
