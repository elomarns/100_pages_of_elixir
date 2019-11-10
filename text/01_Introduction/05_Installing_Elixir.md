### Installing Elixir

As Elixir compiles to Erlang's VM (BEAM), to run code written in Elixir you need to install both of them. The process is pretty easy, but the instructions depend on your operating system.

#### macOS

You can easily install Elixir on macOS using [Homebrew](https://brew.sh/). First, run `brew update` to update your formulas, and then run `brew install elixir`. It will install Elixir and all its dependencies, including Erlang.

#### Ubuntu

Just follow these steps to install Elixir on Ubuntu:

* Add Erlang Solutions repository: `wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb`.
* Update your package lists: `sudo apt-get update`.
* Install Erlang and Elixir: `sudo apt-get install esl-erlang elixir`.

#### Windows

You can install Elixir on Windows using [a very simple installer](https://repo.hex.pm/elixir-websetup.exe), or using the command `cinst elixir` to install with [Chocolatey](https://chocolatey.org/).

#### Other operating systems

If your operating system is not included here, or if you have any problem, take a look at the [official installation instructions](https://elixir-lang.org/install.html).
