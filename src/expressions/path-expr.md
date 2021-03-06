# Path expressions

A [path] used as an expression context denotes either a local
variable or an item. Path expressions that resolve to local or static variables
are [place expressions], other paths are [value expressions]. Using a
[`static mut`] variable requires an [`unsafe` block].

```rust
# mod globals {
#     pub static STATIC_VAR: i32 = 5;
#     pub static mut STATIC_MUT_VAR: i32 = 7;
# }
# let local_var = 3;
local_var;
globals::STATIC_VAR;
unsafe { globals::STATIC_MUT_VAR };
let some_constructor = Some::<i32>;
let push_integer = Vec::<i32>::push;
let slice_reverse = <[i32]>::reverse;
```

[place expressions]: expressions.html#place-expressions-and-value-expressions
[value expressions]: expressions.html#place-expressions-and-value-expressions
[path]: paths.html
[`static mut`]: items/static-items.html#mutable-statics
[`unsafe` block]: expressions/block-expr.html#unsafe-blocks