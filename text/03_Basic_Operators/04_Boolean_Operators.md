### Boolean operators

You can create boolean expressions using boolean operators:

```irb
iex(1)> 10 > 5 and 9 > 7
true
iex(2)> false or true
true
iex(3)> not true
false
```

It's important to know that `and`, `or` and `not` require a boolean value as the first argument, otherwise an error occurs:

```irb
iex(1)> 1 and true
** (BadBooleanError) expected a boolean on left-side of "and", got: 1

iex(1)> :two or false
** (BadBooleanError) expected a boolean on left-side of "or", got: :two

iex(1)> not "almost true"
** (ArgumentError) argument error
    :erlang.not("almost true")
```

But if you want to create a boolean expression where the first operand is not a boolean value you can use `&&`, `||` or `!`:


```irb
iex(1)> :elixir_rocks && "you're breathtaking"
"you're breathtaking"
iex(2)> "Chapter 4 is almost here" || true
"Chapter 4 is almost here"
iex(3)> !300.0
false
```

An important detail about the operators `and`, `or`, `&&` and `||` is the fact they are short-circuit operators. This means they don't run the code on the right side if the left side is enough to get the result:

```irb
iex(1)> false and raise("This exception won't be raised.")
false
iex(2)> true or raise("This exception won't be raised.")
true
iex(3)> false && raise("This exception won't be raised.")
false
iex(4)> true || raise("This exception won't be raised.")
true
```

And if any of the expressions in this section didn't make sense to you, remember that Elixir uses the concept of truthy, so it evaluates anything to `true` except `false` and `nil`.
