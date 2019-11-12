### Integers

You can write integers exactly as you would expect:

```irb
iex(1)> 99
99
```

But you can also add prefixes to write an integer as a hexadecimal (`0x`), octal (`0o`) or binary (`0b`):

```irb
iex(1)> hexadecimal = 0x2A
42
iex(2)> octal = 0o52
42
iex(3)> binary = 0b101010
42
```

And if you're dealing with large numbers, you can use underlines as thousands separators:

```irb
iex(1)> 1_000_000_000
1000000000
```

Elixir just ignores them, but they make it easier to read big numbers. And as we're talking about big numbers, you won't ever need to worry about them. Integers in Elixir don't have a size limit. They'll grow as needed to store your numbers, however big they are.
