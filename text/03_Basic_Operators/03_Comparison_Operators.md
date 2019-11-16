### Comparison operators

You can perform basic comparisons between numbers using the operators shown below:

```irb
iex(1)> 60 == 60
true
iex(2)> 13 != 5
true
iex(3)> 22 > 33
false
iex(4)> 31 >= 31
true
iex(5)> 231 < 85
false
iex(6)> 85 <= 85
true
```

When comparing integers and doubles for equality or inequality you can be more or less strict:

```irb
iex(1)> 132 == 132.0
true
iex(2)> 132 === 132.0
false
iex(3)> 64 != 64.0
false
iex(4)> 64 !== 64.0
true
```

It's also possible to compare data from very different types:

```irb
iex(1)> 1000000000 < :one
true
iex(2)> "two" > :a_very_big_number
true
```

In these cases the comparison follows the following rule:

```elixir
number < atom < reference < function < port < pid < tuple < map < list < bitstring
```

You didn't saw all these data types yet, but you'll learn most of them through the book. And you don't need to memorize this rule. It's not that common to compare such different data types, and if needed you can always check this page.
