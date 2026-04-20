# KaiVim Starter

A starter template for [KaiVim](https://github.com/kev-cao/kaivim), a Neovim
distribution built on [lazy.nvim](https://github.com/folke/lazy.nvim).

## Dependencies

KaiVim requires some external tools. See the
[KaiVim README](https://github.com/kev-cao/kaivim#dependencies) for the full
list.

## Setup

Clone this starter as your Neovim config:

```sh
git clone https://github.com/kev-cao/kaivim-starter.git ~/.config/nvim
```

Launch Neovim. lazy.nvim will automatically install KaiVim and all plugins.

## Structure

```
~/.config/nvim/
├── init.lua              # Bootstraps lazy.nvim and loads KaiVim as a plugin
└── lua/
    └── plugins/          # Your plugin specs (overrides, additions, disables)
        ├── ai.lua        # Enable an AI assistant here
        ├── example.lua
        └── notes.lua     # Enable Obsidian and configure your vault path
```

## Opt-in Plugins

Some plugins are disabled by default in the starter. Enable them in the
corresponding file under `lua/plugins/`:

- **AI assistants** (`lua/plugins/ai.lua`) — enable Claude Code or OpenCode
- **Obsidian** (`lua/plugins/notes.lua`) — enable obsidian.nvim and configure your vault path

## Customization

Add your own plugin specs under `lua/plugins/`. See `lua/plugins/example.lua`
for patterns and the [KaiVim README](https://github.com/kev-cao/kaivim#customization)
for full documentation.

### Examples

**Add a plugin:**

```lua
-- lua/plugins/my-plugins.lua
return {
  { "tpope/vim-commentary" },
}
```

**Override a distribution plugin:**

```lua
-- lua/plugins/overrides.lua
return {
  {
    "navarasu/onedark.nvim",
    opts = { style = "darker" },
  },
}
```

**Disable a distribution plugin:**

```lua
-- lua/plugins/overrides.lua
return {
  { "karb94/neoscroll.nvim", enabled = false },
}
```

## License

[MIT](LICENSE)
