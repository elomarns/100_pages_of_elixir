### One binding per match

If a variable appears more than once in the left side of a matching expression, it will be bound only in its first appearance. After that, Elixir will use the previously bound value to evaluate the match:

```irb
iex(1)> [name, name] = ["Elomar", "Elomar"]
["Elomar", "Elomar"]
iex(2)> [name, name] = ["Elomar", "elomar"]
** (MatchError) no match of right hand side value: ["Elomar", "elomar"]
```

In the first line, Elixir binds `"Elomar"` to `name`, and then it uses that value to match the second element in the list on the right side. But on the second example, the second element in the list is `elomar`, which doesn't match with `Elomar`, so that match fails.

This sample code demonstrates how useful this feature is when you want to check if all values in a data structure are the same.
