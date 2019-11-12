### Dynamic and strong

Elixir is a dynamically typed language. This means you don't assign types to variables, and they can hold values from any data type:

```irb
iex(1)> one = 1
1
iex(2)> one = "one"
"one"
```

Elixir is also strongly typed, which prevents implicit data conversion:

```irb
iex(1)> 41 + "1"
** (ArithmeticError) bad argument in arithmetic expression: 41 + "1"
    :erlang.+(41, "1")
```
