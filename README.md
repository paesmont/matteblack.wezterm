# Matteblack theme for Wezterm

A dark, matte black color scheme for Wezterm based on the original [matteblack.nvim](https://github.com/tahajan/matteblack.nvim) theme.

## Installation

### Option 1: Via config file (recommended)

1. Copy `matteblack.toml` to your Wezterm config directory:
   ```bash
   cp matteblack.toml ~/.config/wezterm/
   ```

2. Add to your `wezterm.lua`:
   ```lua
   local wezterm = require 'wezterm'
   local config = {}

   if wezterm.config_builder then
     config = wezterm.config_builder()
   end

   config.color_scheme_dirs = { '~/.config/wezterm' }
   config.color_scheme = 'matteblack'

   return config
   ```

### Option 2: Direct load

Load the colors directly in your `wezterm.lua`:
```lua
local wezterm = require 'wezterm'

local matteblack = dofile(os.getenv('HOME') .. '/.config/wezterm/matteblack.toml')

local config = {}

if wezterm.config_builder then
  config = wezterm.config_builder()
end

config.colors = matteblack.colors

return config
```

## Credits

- Original theme: [matteblack.nvim](https://github.com/tahajan/matteblack.nvim) by Taha Nejad
- This is a Wezterm port of the original Neovim colorscheme

## License

MIT License - see [LICENSE](LICENSE) file
