### Using existing values

You can use the existing value of a variable in the left side of a pattern matching expression with the pin operator (`^`):

```irb
iex(1)> best_pizza_topping = "Pepperoni"
"Pepperoni"
iex(2)> ^best_pizza_topping = "Pepperoni"
"Pepperoni"
iex(3)> ^best_pizza_topping = "Bacon"
** (MatchError) no match of right hand side value: "Bacon"
iex(3)> [^best_pizza_topping, the_second_best_pizza_topping, _] = ["Pepperoni", "Bacon", "Mushrooms"]
["Pepperoni", "Bacon", "Mushrooms"]
```

First, the value `Pepperoni` is bound to the variable `best_pizza_topping`, and then it's used in the following matches.
