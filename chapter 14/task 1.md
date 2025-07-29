HC14T1: Initialize a Cabal Project

### ✅ Step-by-Step Guide

#### 🛠 1. Initialize the Project

Open a terminal and run:

```bash
cabal init
```

Answer the prompts like this:

* Package name: `hello-cabal`
* Package type: `Executable`
* Module name: `Main`
* License: `MIT` (or your choice)
* Source directory: `src`
* Continue with defaults for the rest.

This creates a directory structure like:

```
hello-cabal/
├── CHANGELOG.md
├── LICENSE
├── README.md
├── hello-cabal.cabal
└── src/
    └── Main.hs
```

---

#### 📝 2. Write the `Main.hs` file

Inside `src/Main.hs`, write the following:

```haskell
-- src/Main.hs
module Main where

main :: IO ()
main = putStrLn "Hello, Cabal!"
```

---

#### 🔧 3. Ensure `hello-cabal.cabal` Looks Correct

Make sure your `.cabal` file has this under the `executable` section:

```cabal
executable hello-cabal
  main-is:             Main.hs
  hs-source-dirs:      src
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010
```

---

#### ▶️ 4. Build and Run

Now build and run your project:

```bash
cabal build
cabal run
```

---

### ✅ Output

```
Hello, Cabal!
```
