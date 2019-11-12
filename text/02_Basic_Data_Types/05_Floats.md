### Floats

Elixir also offers support for floating-point numbers. When writing a float, you must provide at least one digit before and after the decimal point:

```irb
iex(1)> 1.2
1.2
iex(2)> 123.456
123.456
iex(3)> .0
** (SyntaxError) iex:3: syntax error before: '.'
```

Optionally, you can write floats using the character `e` for exponential notation:

```irb
iex(1)> 1.0e1
10.0
iex(2)> 1.0e2
100.0
iex(3)> 1.0e3
1.0e3
iex(4)> 1.0e-1
0.1
iex(5)> 1.0e-2
0.01
iex(6)> 1.0e-3
0.001
```

Elixir implements the standard [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754) for floating-point arithmetic, using the format with 64 bits (double precision).
