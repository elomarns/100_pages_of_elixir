### Namespaces are illusions 

When creating your modules, you can put them inside namespaces:

```irb
iex(1)> defmodule MySuperCoolGame.Player do
...(1)> end
```

Even though it seems you're creating a module inside a namespace, it's just a regular module. You don't need to have a module named `MySuperCoolGame`, and if you have it, it doesn't have any intrinsic relationship with `MySuperCoolGame.Player`. For Elixir, these modules are not related at all. The sole purpose of namespaces in Elixir is to inform other developers about modules with related purposes.
