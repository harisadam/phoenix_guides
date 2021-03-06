In the [Overview Guide](http://www.phoenixframework.org/docs/overview) we got a look at the Phoenix ecosystem and how the pieces interrelate. Now it's time to install any software we might need before we jump into the [Up and Running Guide](http://www.phoenixframework.org/docs/up-and-running).

Please take a look at this list and make sure to install anything necessary for your system. Having dependencies installed in advance can prevent frustrating problems later on.

### Elixir

Phoenix is written in Elixir, and our application code will also be written in Elixir. We won't get far in a Phoenix app without it! The Elixir site maintains a great [Installation Page](http://elixir-lang.org/install.html) to help.

If we have just installed Elixir for the first time, we will need to install the Hex package manager as well. Hex is necessary to get a Phoenix app running (by installing dependencies) and to install any extra dependencies we might need along the way.

Here's the command to install Hex:

```console
$ mix local.hex
```

### Erlang

Elixir code compiles to Erlang byte code to run on the Erlang virtual machine. Without Erlang, Elixir code has no virtual machine to run on, so we need to install Erlang as well.

When we install Elixir using instructions from the Elixir [Installation Page](http://elixir-lang.org/install.html),  we will usually get Erlang too. If Erlang was not installed along with Elixir, please see the [Erlang Instructions](http://elixir-lang.org/install.html#installing-erlang) section of the Elixir Installation Page for instructions.

### Phoenix

Once we have Elixir and Erlang, we are ready to install the Phoenix mix archive. A mix archive is a zip file which contains an application as well as its compiled beam files. It is tied to a specific version of the application. The archive is what we will use to generate a new, base Phoenix application which we can build from.

Here's the command to install the Phoenix archive.

```console
$ mix archive.install https://github.com/phoenixframework/phoenix/releases/download/v0.13.1/phoenix_new-0.13.1.ez
```
> Note: if the Phoenix archive won't install properly with this command, we can download the file directly from our browser, save it to the filesystem, and then run: `mix archive.install /path/to/local/phoenix_new.ez`.

### Plug, Cowboy and Ecto

Those are either Elixir or Erlang projects which are part of Phoenix applications by default. We won't need to do anything special to install them besides `mix deps.get`. If we let mix install our dependencies as we create our new application, we won't even need to do that.

### node.js (>= 0.12.0)

Node is an optional dependency. Phoenix will use brunch.io to compile static assets (javascript, css, etc), by default. Brunch.io uses the node package manager (npm) to install its dependencies, and npm requires node.js.

If we don't have any static assets, or we want to use another build tool, we can pass the `--no-brunch` flag when creating a new application and node won't be required at all.

We can get node.js from the [download page](https://nodejs.org/download/). When selecting a package to download, it's important to note that Phoenix requires version 0.12.0 or greater.

Mac OS X users can also install node.js via [homebrew](http://brew.sh/).

### PostgreSQL

PostgreSQL is a relational database server. Phoenix configures applications to use it by default, but we can switch to MySQL by passing the `--database mysql` flag when creating a new application.

When we work with Ecto models in these guides, we will use PostgreSQL and the Postgrex adapter for it. In order to follow along with the examples, we should install PostgreSQL. The PostgreSQL wiki has [installation guides](https://wiki.postgresql.org/wiki/Detailed_installation_guides) for a number of different systems.

Postgrex is a direct Phoenix dependency, and it will be automatically installed along with the rest of our dependencies as we start our app.

### inotify-tools (for linux users)

This is a Linux-only filesystem watcher that Phoenix uses for live code reloading. (Mac OS X or Windows users can safely ignore it.)

Linux users need to install this dependency. Please consult the [inotify-tools wiki](https://github.com/rvoicilas/inotify-tools/wiki) for distribution-specific installation instructions.
