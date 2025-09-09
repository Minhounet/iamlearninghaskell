iamlearninghaskell

This is my project to learn haskell.

[[_TOC_]]

# Prerequisites

I assume you are using a Linux environment (or WSL like me, it makes things easier).
You will need to install ghcup (to install haskell compiler and handle versions of ghc), Stack (to develop Haskell projects) and if you want Intellij.

## Install Haskell stuff

There are two ways to install, the recommanded one which stucks at "cabal update" for me.

First of first, uninstall all existing stack/cabal/ghc to start on a clean environment then...


### Standard way

```bash
# Install ghcup (and follow instructions)
curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | bash
```

This method did not work because it got stucked during "cabal update" (download the script if you are curious)

### Terminal way

```bash
~/.ghcup/bin/ghcup tui
# Then install for example all recommanded items
# don't forget to "install" and to "set"

# Also update your PATH and add "~/.ghcup/bin/ghcup/bin" in your rc file (for me it is .bashrc)
echo "export PATH=\"$HOME/.ghcup/bin:\$PATH\"" >> ~/.bashrc
source ~/.bashrc
```

# Build

```bash
# build the project
stack build
```

# Troubleshooting

## Error during creating new project with stack

I ran an issue when creating a new project with stack
👉add the following lines into you ~/.stack/config.yaml

```bash
vi ~/.stack/config.yaml
```

and add the following lines:
```
urls:
  latest-snapshot: https://stackage-haddock.haskell.org/snapshots.json
```

# Author

Minh
