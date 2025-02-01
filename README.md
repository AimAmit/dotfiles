```
# Dotfiles Repository

This repository contains all the configurations for various tools and environments, including:

- Neovim (`~/.config/nvim`)
- Tmux (`~/.tmux`)
- Zsh (`~/.zshrc`, `~/.config/zsh`)

## Table of Contents

- [Neovim](#neovim)
- [Tmux](#tmux)
- [Zsh](#zsh)
- [Adding a New Configuration](#adding-a-new-configuration)
- [Retrieving Existing Configurations](#retrieving-existing-configurations)

## Neovim

### Adding Neovim Config to Dotfiles

1. If `~/.config/nvim` is a git repo and you want to add it as a submodule:
    ```bash
    dotfiles submodule add <your-nvim-repo-url> ~/.config/nvim
    dotfiles commit -m "Added Neovim config as a submodule"
    dotfiles push origin main
    ```

2. If `~/.config/nvim` is not a git repo, just add it to `dotfiles`:
    ```bash
    rm -rf ~/.config/nvim/.git
    dotfiles add ~/.config/nvim
    dotfiles commit -m "Added Neovim config"
    dotfiles push origin main
    ```

3. If you want to track Neovim in a separate directory:
    ```bash
    mv ~/.config/nvim ~/dotfiles/nvim
    ln -s ~/dotfiles/nvim ~/.config/nvim
    dotfiles add ~/dotfiles/nvim
    dotfiles commit -m "Added Neovim config via symlink"
    dotfiles push origin main
    ```

### Retrieving Neovim Config

To retrieve and apply your Neovim config on a new machine:
```bash
git clone <dotfiles-repo-url> ~/.dotfiles
cd ~/.dotfiles
./install.sh  # If you have an install script for symlinks
```

Then, ensure Neovim config is correctly symlinked or cloned based on your preference.

## Tmux

### Adding Tmux Config to Dotfiles

To add your Tmux configuration:
```bash
dotfiles add ~/.tmux
dotfiles commit -m "Added Tmux config"
dotfiles push origin main
```

### Retrieving Tmux Config

To retrieve and apply your Tmux config on a new machine:
```bash
git clone <dotfiles-repo-url> ~/.dotfiles
cd ~/.dotfiles
./install.sh  # Or manually symlink ~/.tmux
```

## Zsh

### Adding Zsh Config to Dotfiles

To add your Zsh configuration:
```bash
dotfiles add ~/.zshrc
dotfiles add ~/.config/zsh
dotfiles commit -m "Added Zsh config"
dotfiles push origin main
```

### Retrieving Zsh Config

To retrieve and apply your Zsh config on a new machine:
```bash
git clone <dotfiles-repo-url> ~/.dotfiles
cd ~/.dotfiles
./install.sh  # Or manually symlink ~/.zshrc and ~/.config/zsh
```

## Adding a New Configuration

To add a new config file or folder:

1. Place your configuration file in the appropriate location (e.g., `~/.config/nvim`, `~/.tmux`, `~/.zshrc`).
2. Add the file to the `dotfiles` repository:
    ```bash
    dotfiles add <file-or-folder>
    ```
3. Commit and push the change:
    ```bash
    dotfiles commit -m "Added new config for <tool>"
    dotfiles push origin main
    ```

## Retrieving Existing Configurations

To retrieve your existing configurations on a new machine:

1. Clone your `dotfiles` repository:
    ```bash
    git clone <dotfiles-repo-url> ~/.dotfiles
    ```

2. Run the setup script (if any) or manually create symlinks to the configuration files:
    ```bash
    cd ~/.dotfiles
    ./install.sh  # If you have an install script for symlinks
    ```

Or manually symlink the individual files as needed:
```bash
ln -s ~/.dotfiles/nvim ~/.config/nvim
ln -s ~/.dotfiles/tmux ~/.tmux
ln -s ~/.dotfiles/zshrc ~/.zshrc
ln -s ~/.dotfiles/zsh ~/.config/zsh
```
```

This raw content provides a clear structure to manage your dotfiles, with instructions on adding and retrieving specific configurations for Neovim, Tmux, and Zsh. You can easily copy this into your `README.md` file and adjust it as per your setup.
