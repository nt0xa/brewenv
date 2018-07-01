# brewenv

brewenv allows you easily manage and switch between multiple Homebrew environments.
In fact, it is just helps you to download Homebrew to selected directory and hooks your `$PATH`.

## Installation

### From git

1. Clone the repository:

```sh
$ git clone https://github.com/russtone/brewenv ~/.brewenv
```

2. Add `brewenv` to your `$PATH`:

```sh
export PATH="$HOME/.brewenv:$PATH"
```

3. Set your `$BREWENV_HOME` (place, where your global environments will be placed):

```sh
export BREWENV_HOME="$HOME/.brewenv"
```

4. Add this lines to your `.bashrc` or `.zshrc`:

```sh
if command -v >/dev/null 2>&1; then
  eval "$(brewenv init -)"
fi
```

## Usage

### Global environments

Global environments are installations of Homebrew created in your `$BREWENV_HOME/environments` directory.

```sh
# Create new global environment
$ brewenv create -g pentest
Downloading homebrew...
Homebrew successfully downloaded to '/Users/russtone/.local/share/brewenv/environments/pentest'

# Switch to created environment
$ brewenv activate -g pentest
$ which brew
/Users/russtone/.local/share/brewenv/environments/pentest/bin/brew

# Install some Homebrew stuff
...

# Switch back to default environment
$ brewenv deactivate
$ which brew
/usr/local/bin/brew
```

### Local envrionments

Local environments are more like per project installations of Homebrew.

```sh
# Go to your project directory
$ cd ~/Projects/some-project

# Create local Homebrew environment in current project directory
$ brewenv create benv
Downloading homebrew...
Homebrew successfully downloaded to 'benv'

# Switch to your local Homebrew environment
$ brewenv activate benv
$ which brew
/Users/russtone/Projects/some-project/benv/bin/brew

# Install some Homebrew stuff
...

# Switch back to default environment
$ brewenv deactivate
$ which brew
/usr/local/bin/brew
```
