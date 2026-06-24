# dotfiles

Personal macOS dotfiles and bootstrap scripts, managed with [chezmoi](https://www.chezmoi.io/).

## Overview

This repository contains:

- Shell configuration (`zsh` with [Oh My Zsh](https://ohmyz.sh/)).
- A curated list of CLI tools and applications installed via [Homebrew](https://brew.sh/).
- Bootstrap scripts that turn a fresh macOS install into a working environment.

## Prerequisites

- macOS (Apple Silicon or Intel).
- [Xcode Command Line Tools](https://developer.apple.com/xcode/resources/) (installed automatically if missing).

## Installation

On a new machine, run:

```sh
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply RBFernando99
```

This will:

1. Install chezmoi.
2. Clone this repository.
3. Run the bootstrap scripts (Homebrew, packages, Oh My Zsh plugins).
4. Apply the dotfiles to your home directory.

## What gets installed

See [`.chezmoidata/packages.yaml`](.chezmoidata/packages.yaml) for the full list. Highlights:

- **Shell tooling:** `starship`, `atuin`, `zoxide`, `fzf`, `eza`, `bat`, `ripgrep`, `tmux`.
- **Apps:** `ghostty`.
- **Fonts:** `font-jetbrains-mono-nerd-font`.
- **Oh My Zsh plugins:** `zsh-autosuggestions`, `zsh-syntax-highlighting`, `zsh-completions`.

## Usage

Edit a managed file:

```sh
chezmoi edit ~/.zshrc
chezmoi apply
```

Start managing a new dotfile:

```sh
chezmoi add ~/.config/starship.toml
```

Add or remove a package: edit [`.chezmoidata/packages.yaml`](.chezmoidata/packages.yaml) and run `chezmoi apply`.

Commit and push changes:

```sh
chezmoi cd
git add -A && git commit -m "..." && git push
exit
```

Pull changes made on another machine:

```sh
chezmoi update
```

## License

Released into the public domain under [The Unlicense](LICENSE).
