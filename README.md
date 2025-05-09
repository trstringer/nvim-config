# Neovim (and tmux) config

## Backup

```bash
backup.sh
git add .
git commit -m "New neovim config"
```

## Restore

```bash
# Install neovim release that matches the version.

# Restore Lazy plugins.
cp ./lazy-lock.json ~/.config/nvim/
nvim
# :Lazy restore

# Restore Mason LSPs.
cp ./mason-lock.json ~/.config/nvim/
nvim
# :MasonLockRestore

# Restore editorconfig
cp ./.editorconfig ~

# Restore vim helpers
cp ./.vim_helpers.sh ~
# Source it in bashrc
if ! grep vim_helpers ~/.bashrc ; then
    echo "source /home/trstringer/.vim_helpers.sh" >> ~/.bashrc
fi

# Restore tmux
cp ./.tmux.conf ~

# Restore terminal themes
cp ~/.local/share/nvim/lazy/tokyonight.nvim/extras/xfceterm/*.theme ~/.local/share/xfce4/terminal/colorschemes/

# Restore xfce4-terminal settings
cp ./xfce4-terminal.xml ~/.config/xfce4/xfconf/xfce-perchannel-xml/
```
