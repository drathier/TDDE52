# What's Purescript?
- Pure functional programming language
  - Most of the time we build and transform immutable data structures
  - Usually results in shorter programs, which are easier to test
  - Ever used someArray.map(function(x) {...}) in javascript? That's taken from pure functional programming.
- "Haskell 2.0", if that helps

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
- The compiler caching task is too large for this course, but there's so many much much easier tasks to do.
- Some changes are hard to get merged, others get merged in minutes.
- Discord channel with real experts on the compiler code base
- Compilers and languages NOT black magic! You can do this too!
