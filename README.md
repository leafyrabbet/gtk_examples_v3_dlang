# GTK+ v3 Examples (D Language)

## Build and Setup

### macOS Catalina (10.15.x)

Note that with macOS Catalina (10.15.x), Apple changed the default shell for the system and user accounts to be `zsh` instead of `bash`. You shouldn't need to change it to run anything here, but I built everything using `bash` instead of `zsh`, so for reference here's how I updated my config:

```zsh
chsh -s /bin/bash;
touch ~/.bash_profile;
touch ~/.bashrc;
echo "source ~/.bashrc" >> ~/.bash_profile;
```

And then you can use either `~/.bashrc` or `~/.bash_profile` to put your shell preferences in. As configured, it's preferable to put everything in `~/.bashrc` since that'll be `source`-ed (read: "imported") by the `~/.bash_profile` file. I do this typically just to try and keep things more comparable to Linux systems that I use and work with, since they tend to only use a `~/.bashrc` config file and don't have the `~/.bash_profile` version. Most (if not all) of the configs are compatible between macOS and Linux, so putting everything into `~/.bashrc` this way can make the config more portable and reusable.

Again, the above is optional, but it's what I did, so there may be `bash`-specific commands referenced, and if you're using `zsh` you may get errors that I didn't. So please just be aware of that so that you don't get stuck or post a config-specific issue. If you'd like to request `zsh` support for this repo, please create an Enhancement issue on GitHub.

For the rest of the setup, the steps we'll follow are:

1. Install Homebrew, to make library installations consistent and (relatively) config-proof.
1. Use Homebrew to install the GTK+ v3 library and its dependencies.
1. Download and install a macOS compatible D Language Compiler.
1. Download the `gtkd` source code.
1. Build and install `gtkd`.

This process, all together, should take about 30-60 minutes with downloads and depending on your system specs.

- [Homebrew](https://brew.sh/) install:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

- Homebrew install GTK+ v3 to macOS system:

```bash
brew install gtk+3;
brew install gtkmm3;  # Optional, C++ bindings in-case you want to do C++ development.
```

- D Lanaguage compiler (`dmd`) install:

> _Note_: `gcc-9` is supported by Homebrew and it's true that `gdc` was pulled into mainline `gcc-9` releases, but unfortunately it's not currently supported in the Homebrew install of `gcc-9` for macOS systems. There's a patch or two out there to support it, but it seems like there's some D Standard Library (`phobos`) config/install "issues" with macOS, so it's likely it won't be included in the official Homebrew version until `gcc-10`. So, instead of using `gdc`, we'll just use the link above to install `dmd` from the `.pkg` file provided by the downloadable `.dmg` container.

- Download `gtkd` source code:
- untar and navigate into source directory, then run GNU Make to build and install `gtkd`.

## References

- [GTK+ Website]()
- [gtkd Website]()
- [D Language](https://www.dlang.org)

- https://www.howtogeek.com/444596/how-to-change-the-default-shell-to-bash-in-macos-catalina/
- https://www.cyberciti.biz/faq/change-default-shell-to-bash-on-macos-catalina/

## Copyright

All rights reserved.

Copyright 2020, LeafyRabbet (TenonGarden Productions)

