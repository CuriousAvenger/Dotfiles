# Dotfiles

This repository contains my personal dotfiles and configuration for Zsh, Tmux, and terminal appearance on Ubuntu systems. It uses [GNU Stow](https://www.gnu.org/software/stow/) for easy management and symlinking.

## Prerequisites

Make sure you have `git` installed:
```bash
sudo apt update && sudo apt install git
```

## 1. Install Zsh

```bash
sudo apt install zsh
chsh -s $(which zsh)
```

### Install Zinit (Zsh Plugin Manager)

Zinit is a flexible and fast Zsh plugin manager. You’ll need `unzip` to install it:

```bash
sudo apt install unzip
sh -c "$(curl -fsSL https://git.io/zinit-install)"
```

Restart your terminal or run `zsh` to use Zinit.

## 2. Install Oh My Posh

[Oh My Posh](https://ohmyposh.dev/) is a prompt theme engine for many shells including Zsh.

```bash
sudo apt install wget
wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/oh-my-posh-linux-amd64
sudo mv oh-my-posh-linux-amd64 /usr/local/bin/oh-my-posh
sudo chmod +x /usr/local/bin/oh-my-posh
```

You can add an Oh My Posh initialization line to your `.zshrc` (included in this dotfiles repo).

## 3. Install Tmux

```bash
sudo apt install tmux
```

### Install TPM (Tmux Plugin Manager)

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

After starting tmux, use `prefix + I` (usually `Ctrl+b I`) to install plugins.

## 4. Manage Dotfiles with GNU Stow

[Gnu Stow](https://www.gnu.org/software/stow/) helps you organize your dotfiles by symlinking them from their respective folders.

Install stow:
```bash
sudo apt install stow
```

Clone this repository:
```bash
git clone https://github.com/CuriousAvenger/Dotfiles.git ~/Dotfiles
cd ~/Dotfiles
```

Symlink your configs (example for zsh and tmux):
```bash
stow zsh
stow tmux
```

You can stow other configs as needed (e.g., `stow nvim`, `stow git`, etc.).

## 5. Final Steps

- Start a new terminal session or source your `.zshrc`:
  ```bash
  source ~/.zshrc
  ```
- Start tmux and press `Ctrl+b I` to install TPM plugins.

---

## Folder Structure

```
Dotfiles/
├── zsh/
│   └── .zshrc
├── tmux/
│   └── .tmux.conf
├── other/
│   └── ...
```

Each directory contains configuration files for that tool. Use stow to symlink them to your `$HOME`.

---

Feel free to customize these instructions for your workflow!
