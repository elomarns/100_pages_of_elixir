### Running Elixir code

When you install Elixir, besides `iex`, you also get 2 executables to compile and run your code: `elixir` and `elixirc`.

`elixir` is the most straightforward way to run your Elixir code. First, just create an `.exs` file containing some code:

```elixir
IO.puts "This is not a Hello World. I swear!"
```

Then run it from the terminal:

```console
$ elixir not_a_hello_world.exs
This is not a Hello World. I swear!
```

`elixir` compiled the file in memory, and then executed it, without leaving any trace of its work.

But if you want to keep the compiled code, you should use `elixirc`. So start by creating an `.ex` file with the following content:

```elixir
defmodule Princess do
  def search do
    IO.puts "The princess is in another castle."
  end
end

Princess.search()
```

Then compile and run this file with `elixirc`:

```console
$ elixirc princess.ex
The princess is in another castle.
```

At first sight, it seems it worked exactly like the `elixir` executable. But if we list the files in this directory, we'll see this is not the case:

```console
$ ls -1
Elixir.Princess.beam
not_a_hello_world.exs
princess.ex
```

Now you have a compiled version of your code in your hard drive. The `.beam` file is the resulting bytecode, which runs on BEAM (Erlang's VM).

And don't worry if you don't understand the code. Everything will make sense in a few chapters. For now, the only important thing is to understand the different ways you can run your code.
