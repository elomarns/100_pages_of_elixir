### You can ignore some values

Elixir has the special variable `_`, which acts as a wildcard in pattern matching expressions, but without doing the binding:

```irb
iex(1)> _ = "I'm feeling I'm being ignored"
"I'm feeling I'm being ignored"
iex(2)> _
** (CompileError) iex:2: invalid use of _. "_" represents a value to be ignored in a pattern and cannot be used in expressions
```

The matching happened, as you can see by the return value, but no binding was performed. And, as you can see above, you can't even access the value of `_`.

However, the code above is not very useful. The variable `_` makes much more sense when you're trying to match a compound data:

```irb
iex(1)> [my_favorite_language, my_second_favorite_language, _] = ["Elixir", "Ruby", "Fortran"]
["Elixir", "Ruby", "Fortran"]
```

In this piece of code, the first and second values in the list on the right side are being matched and bound to variables. However, I don't care about the third value, so I use the `_` variable, which matches anything, but without doing the binding.
