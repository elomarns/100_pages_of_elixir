### Creating and calling named functions

A named function is a function defined inside a module, and, as you can probably imagine, it must have a name. To make things easier, let's start with one that just prints something to the terminal. To do that, you can use the builtin function `IO.puts`. Don't think too much about it, for now. You only need to know that it prints its argument to the terminal, and then returns the symbol `:ok`:

```irb
iex(1)> IO.puts("It's about time to have a Hello World in this book!")
It's about time to have a Hello World in this book!
:ok
```

Now that you know how to use the `IO.puts` function, you can create a named function to call it. To do that, you must start its declaration with `def`:

```irb
iex(2)> defmodule NotAnAlienDisguisedAsHuman do
...(2)>   def greet do
...(2)>     IO.puts("Hello, fellow Earth citizen!")
...(2)>   end
...(2)> end
```

After that, you can call it by prepending its name with the module name, separating them with a dot:

```irb
iex(3)> NotAnAlienDisguisedAsHuman.greet()
Hello, fellow Earth citizen!
:ok
```

After calling the function `greet`, the message was printed, and then the value `:ok` was returned. This happens because all expressions in Elixir have a return value. In the case of functions, they return the value of the last expression executed in their bodies. And as the function `IO.puts` is the last expression on `greet` body, its return value is also the return value of `greet`.

You can also create functions with parameters:

```irb
iex(4)> defmodule Math do
...(4)>   def double(number) do
...(4)>     number * 2
...(4)>   end
...(4)> 
...(4)>   def sum(a, b) do
...(4)>     a + b
...(4)>   end
...(4)> end
iex(5)> Math.double(22)
44
iex(6)> Math.sum(3, 10)
13
```

One last thing: the parentheses are not mandatory when calling a named function. However, it's a good idea to include them to make things clearer.
