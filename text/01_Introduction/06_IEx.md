### IEx

By installing Elixir, you also get IEx (Interactive Elixir). It allows you to write Elixir code on the terminal and immediately see the result. It's a great tool to learn and to experiment with code. To start it, just type `iex` on your terminal:

```console
$ iex
Erlang/OTP 22 [erts-10.5.1] [source] [64-bit] [smp:4:4] [ds:4:4:10] [async-threads:1] [hipe]

Interactive Elixir (1.9.4) - press Ctrl+C to exit (type h() ENTER for help)
iex(1)>
```

IEx comes with some helpers, and `h` is one of the most useful of them. Without any argument, it displays documentation for the others IEx helpers:

```irb
iex(1)> h

                           IEx.Helpers

Welcome to Interactive Elixir. You are currently seeing the
documentation for the module IEx.Helpers which provides many
helpers to make Elixir's shell more joyful to work with.

This message was triggered by invoking the helper h(), usually
referred to as h/0 (since it expects 0 arguments)...
```

But it can also show you documentation for modules and functions:

```irb
iex(2)> h Enum.map

                    def map(enumerable, fun)

  @spec map(t(), (element() -> any())) :: list()

Returns a list where each element is the result of invoking fun
on each corresponding element of enumerable.

For maps, the function expects a key-value tuple.

## Examples

    iex> Enum.map([1, 2, 3], fn x -> x * 2 end)
    [2, 4, 6]

    iex> Enum.map([a: 1, b: 2], fn {k, v} -> {k, -v} end)
    [a: -1, b: -2]
```

Another important thing to know about IEx is how to exit from it. Just press `Ctrl` +  `C` twice.

It worths to take some time to get familiar with IEx. It's a tool you'll use for your whole journey through Elixir.
