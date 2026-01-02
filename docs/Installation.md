# Neovim Setup

# Mac setup
1. Install Neovim
    ```bash
    brew install neovim
    ```
2. Install JetBrains Mono NerdFont
    ```bash
    brew install --cask font-jetbrains-mono-nerd-font
    ```
    Then set terminal font to JetBrains Mono NerdFont (you can verify if working if you see icons)
    - In Warp, this is Settings -> Appearance -> Text -> Terminal Font (may need to restart terminal to see new font)
3. (Optional) Install Oh My ZSH: https://ohmyz.sh
    - Set the theme in `~/.zshrc`
    ```bash
    ZSH_THEME="amuse"
    ```
4. Install AstroNVim
   Follow instructions: https://docs.astronvim.com/#-installation
5. Install GitHub Copilot
    - Already installed from community plugin
    - Authenticate
    ```bash
    :Copilot auth
    ```
    I've configured Alt l to accept copilot suggestions, so you'll need to configure terminal to see Alt key as meta key
    - In Warp, this is Settings -> Features -> Keys -> Enable "Left Option key is Meta". Restart nvim.
6. Add custom user config at `~/.config/nvim/lua/user/init.lua`
    - [My custom config](./init.lua)
        - set number line to absolute
        - enable spell check
        - enable word wrap
        - added custom key `Space + fg` to search for exact word match
        - assigned key `ff` to the same function as the `<esc>` key
        - highlight selected line that cursor is on
        - enable copiloat autostart

# Troubleshooting
- May get this after installing
```bash
Error detected while processing /Users/yourname/.config/nvim/init.lua:
E5113: Error while calling lua chunk: Vim:E739: Cannot create directory /Users/yourname/.local/state/nvim: permission denied
stack traceback:
```
- Give yourself access
```bash
sudo chown -R "$USER" ~/.local/state
# Check
ls -ld ~/.local ~/.local/state ~/.local/share
```