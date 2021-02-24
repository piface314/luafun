# Changelog

This changelog refers to changes made on Lua Fun after being forked on [commit e248e00](https://github.com/luafun/luafun/commit/e248e007be4d3474224277f6ba50f53d4121bfe0).

## Changed
- `reduce`/`foldl` argument order reversed (start value comes first).
- `iter` only considers a table as an array when it contains strictly only consecutive numeric indexes, by testing: `#obj > 0 and next(obj, #obj) == nil`.
- `iter`, when called with an iterator triplet, now creates a generator that duplicates the first returned value during iteration (the new state), to keep things aligned to how default Lua functions like `pairs` work, and to allow functions like `string.gmatch` or `io.lines` to be used as iterators, since they have no state.