### Pattern matching is your new best friend

I told you in the last chapter that pattern matching was one of the most important concepts in Elixir, and I've meant it. You can see its presence everywhere, including when you call a function:

```irb
iex(1)> multiply = fn a, b -> a * b end
#Function<13.91303403/2 in :erl_eval.expr/5>
iex(2)> multiply.(9, 6)
54
```

When you call a function with arguments, Elixir sees it as a pattern matching expression. The arguments you pass are the terms, and the parameters in the function definition are the patterns. So, in this example, I have two patterns which are just variables (`a` and `b`), and they match by binding the terms passed as arguments (`9` and `6` ).

It may seem I'm over complicating what should be a simple function call, but you're about to see how pattern matching can change the way you create and call functions.
