### Arithmetic operators

Elixir has all the usual arithmetic operators:

```irb
iex(1)> 200 + 57
257
iex(2)> 10 - 7
3
iex(3)> 437 * 3
1311
iex(4)> 100 / 8
12.5
```

As you can see above, the operator `/` always returns a float value. If you want to do integer division you must use the function `div`:


```irb
iex(1)> div(100, 8)
12
```

You can also get the remainder of a division with the function `rem`:

```irb
iex(1)> rem(100, 8)
4
```

And don't worry if you don't understand how functions work in Elixir. I'll talk about them in a few chapters.
