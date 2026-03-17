# Matteblack theme for Wezterm

A dark, matte black color scheme for Wezterm based on the original [matteblack.nvim](https://github.com/tahajan/matteblack.nvim) theme.

## Installation

### Via Wezterm's built-in theming

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

   config.color_scheme = 'matteblack'

   return config
   ```

### Manual

Reference the theme directly in your `wezterm.lua`:
```lua
local wezterm = require 'wezterm'
local colors = wezterm.color.get_builtin_colorschemes()['matteblack']
-- or load from file
local colors = dofile(os.getenv('HOME') .. '/.config/wezterm/matteblack.toml')
```

## Credits

- Original theme: [matteblack.nvim](https://github.com/tahajan/matteblack.nvim) by Taha Nejad
- This is a Wezterm port of the original Neovim colorscheme

## License

MIT License - see [LICENSE](LICENSE) file
