### Booleans

Like most programming languages, Elixir has only two boolean values: your old pals `true` and `false`.

```irb
iex(1)> true
true
iex(2)> false
false
```

However, there's a dirty secret about them: they're actually the atoms `:true` and `:false`.

```irb
iex(1)> true == :true
true
iex(2)> false == :false
true
```

But you shouldn't worry about it, this is just their internal representation. It doesn't change anything about how they work.

It worths to mention there's also the `nil` value, even though it's not a boolean value. Actually it represents the absence of a value, and it's an atom behind the scenes too:

```irb
iex(1)> nil == :nil
true
```

It's relevant to talk about `nil` here because Elixir has the concept of truthy. If a value is not `false` or `nil`, it's truthy, which works as the same as `true` in almost all cases.
