# What's Purescript?
- Pure functional programming language
  - you describe what should happen, instead of step-by-step doing the changes yourself
- Think "Haskell 2.0"

# What we did
- Edvard: Standard library changes. Compiler error messages. 
- Erik: Build cache handling; cleaning up the build output folder when build inputs are removed.
- Filip: Compiler caching. Standard library changes.

# What I did: Compiler caching
- A imports B, which imports C, etc.
- A -> B -> C -> D -> E -> F
- Previously, if B changed, everything that imported B was recompiled.
- Now we only recompile if the public api of the module changed.

# Example:
```
iex(84)> r
PurerlEx: assuming the project root is `/Users/drathier/lesslie/code/pay-backend`
purs compile: No files found using pattern: src/**/*.purs
[  1 of 259] Compiling Lesslie.Fortnox.Bookkeeping
[  2 of 259] Compiling Lesslie.Fortnox.BookkeepingTest
[  3 of 259] Compiling Lesslie.Fortnox.Background
[  4 of 259] Compiling Test.Main

[info] Build succeeded.
```
- [  4 of 259]
- 259 files would have been recompiled before
- we stopped after 4 recompiled modules, because the public api was the same

# Should I contribute to Purescript?
- If you have an interest in pure functional programming
- A week of Elm is plenty to know if you'll like working with it 
- There's lots and lots of low-hanging fruit once you get there, but interest in pure functional programming is basically required, since it's so different from C-style languages. Not hard, but different.
- Some changes are hard to get merged, others get merged in minutes.
- Discord channel with real experts on the compiler code base
- Compilers and languages NOT black magic! You can do this too!
