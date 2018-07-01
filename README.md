# brewenv

brewenv allows you easily manage and switch between multiple Homebrew environments.
In fact, it is just helps you to download Homebrew to selected directory and hooks your `$PATH`.

## Installation

### From git

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
