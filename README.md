# brewenv

brewenv allows you easily manage and switch between multiple Homebrew environments.

## Installation

### From git

## Usage

```sh
# Create new global environment
$ brewenv create -g pentest
Downloading homebrew...
Homebrew successfully downloaded to '/Users/russtone/.local/share/brewenv/environments/pentest'

# Switch to created environment
$ brewenv activate -g pentest
$ which brew
/Users/russtone/.local/share/brewenv/environments/pentest/bin/brew

# Switch back to default environment
$ brewenv deactivate
$ which brew
/usr/local/bin/brew
```

