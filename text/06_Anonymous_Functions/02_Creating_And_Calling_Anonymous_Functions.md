### Creating and calling anonymous functions

Unsurprisingly, an anonymous function is a function without a name. But it's a value like any other, so you can bind it to a variable. You can also pass it to other functions as arguments, and that's why most anonymous functions are created.

A good anonymous function to start is one that just prints something to the terminal. To do that, you can use the builtin function `IO.puts`. Don't think too much about it, for now. You only need to know that it prints its argument to the terminal, and then returns the symbol `:ok`:

```irb
iex(1)> IO.puts("It's about time to have a Hello World in this book!")
It's about time to have a Hello World in this book!
:ok
```

Now that you know how to use the `IO.puts` function, you can create an anonymous function to call it. To do that you must surround the function code by `fn ->` and `end`:

```irb
iex(2)> say_hello = fn -> IO.puts("Hello!") end
#Function<21.91303403/0 in :erl_eval.expr/5>
```

Then you can call this function adding `.()` after the variable name:

```irb
iex(3)> say_hello.()
Hello!
:ok
```

You can see above the symbol `:ok` being returned. Everything in Elixir has a return value, and functions return the last value evaluated in their bodies. So our function returns the value returned by `IO.puts`, which is the symbol `:ok`.

Even though the function was bound to a variable in this example, you can also call a literal anonymous function:

```irb
iex(4)> fn -> IO.puts("I don't need a variable!") end.()
I don't need a variable!
:ok
iex(5)> (fn -> IO.puts("I don't need a variable!") end).()
I don't need a variable!
:ok
```

You don't need the parentheses around the function definition, but it makes much easier to read it. On the other hand, you must include a dot before the function call, so it's clear that you're calling an anonymous function, and not a named one.

You can also create anonymous functions with parameters:

```irb
iex(6)> say = fn something -> IO.puts(something) end
#Function<7.91303403/1 in :erl_eval.expr/5>
iex(7)> say.("Hello to my little friend")
Hello to my little friend
:ok
iex(8)> add = fn a, b -> a + b end
#Function<13.91303403/2 in :erl_eval.expr/5>
iex(9)> add.(5, 3)
8
iex(10)> add = fn (a, b) -> a + b end
#Function<13.91303403/2 in :erl_eval.expr/5>
iex(11)> add.(5, 3)                  
8
```

The list of parameters is separated by commas, and may or may not be surrounded by a pair of parentheses.
