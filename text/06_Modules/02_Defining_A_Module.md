### Defining a module

To create a module, you must start its definition with `defmodule`:

```irb
iex(1)> defmodule Player do
...(1)> end
{:module, Player,
 <<70, 79, 82, 49, 0, 0, 3, 128, 66, 69, 65, 77, 65, 116, 85, 56, 0, 0, 0, 120,
   0, 0, 0, 12, 13, 69, 108, 105, 120, 105, 114, 46, 80, 108, 97, 121, 101, 114,
   8, 95, 95, 105, 110, 102, 111, 95, 95, ...>>, nil}
```

Here we have an empty module called `Player`. Module names must use the `CamelCase` convention. So, each word must start with a UTF-8 uppercase letter, followed by lowercase letters or numbers, and with no space between words. These are all valid module names:

```plaintext
Database
PlayerInput
RandomFactGenerator
```

Additionally, even though I'm using IEx to illustrate Elixir concepts, you should know that module definitions are stored in files. Each module has its own file, with the same name as the module, but using the `snake_case` convention. For example, the module defined above would be stored in a file called `player.ex`, or `player.exs`.
