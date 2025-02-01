# Dotfiles

This repository contains configuration files for various tools such as Neovim, Tmux, Zsh, and more.

## Getting Started

### Clone the Repository

To get started, clone the repository into your home directory:

```sh
git clone --bare https://github.com/AimAmit/dotfiles.git $HOME/.dotfiles
```

### Install the Configurations

Once cloned, use the following command to symlink all the configuration files:

```sh
cd ~
git --git-dir=$HOME/.dotfiles --work-tree=$HOME checkout
```

This will set up all configurations (Neovim, Tmux, Zsh, etc.) directly into your home directory.

### To Add New Config Files

1. **Navigate to the configuration file** you want to add (e.g., for Neovim, Tmux, or Zsh).
2. **Add the new file** to the dotfiles repo using the command below:

   ```sh
   dotfiles add <path_to_file_or_directory>
   ```

3. **Commit the changes**:

   ```sh
   dotfiles commit -m "Added new config for <config_name>"
   ```

4. **Push the changes to the repository**:

   ```sh
   dotfiles push
   ```

This will add your new configuration file to the repo and sync it with the remote.

### Syncing Configuration Files

To update or sync the configurations from the remote repository, simply run:

```sh
git --git-dir=$HOME/.dotfiles --work-tree=$HOME pull
```

### Removing a Configuration File

If you want to stop syncing a file, first remove the symlink and then commit the changes:

```sh
rm ~/.config/<config_file>
dotfiles commit -m "Removed <config_name> config"
dotfiles push
```

### Install Dependencies

Some configurations may require additional dependencies like plugins or other software. You can install dependencies by following the respective instructions in the configuration files, for example:

- For Neovim, use `:PlugInstall` or any other plugin manager you're using.
- For Tmux, use `tmux plugin manager (TPM)`.

### Troubleshooting

- If you encounter issues with symlinks or file conflicts, ensure that the `.config` directory is not part of the repository.
- To reset all configurations, simply delete the `~/.dotfiles` directory and start the setup again.

## Configuration Files

- **Neovim**: Configurations located under `~/.config/nvim`.
- **Tmux**: Configurations under `~/.tmux`.
- **Zsh**: Configurations under `~/.zshrc`.

You can add or remove configurations by editing the relevant files in this repository.
