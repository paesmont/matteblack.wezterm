# Matteblack theme for Wezterm

A dark, matte black color scheme for Wezterm based on the original [matteblack.nvim](https://github.com/tahajan/matteblack.nvim) theme.

## Installation

### Option 1: Via load_scheme (recommended)

1. Create a `colors` directory in your Wezterm config:
   ```bash
   mkdir -p ~/.config/wezterm/colors
   ```

2. Copy `matteblack.toml` to that directory:
   ```bash
   cp matteblack.toml ~/.config/wezterm/colors/
   ```

3. Add to your `wezterm.lua` (use ABSOLUTE path, not `$HOME`):
   ```lua
   local wezterm = require 'wezterm'

   -- Load the color scheme (use absolute path!)
   wezterm.color.load_scheme(os.getenv('HOME') .. '/.config/wezterm/colors/matteblack.toml')

   local config = {}

   if wezterm.config_builder then
     config = wezterm.config_builder()
   end

   config.color_scheme = 'matteblack'

   return config
   ```

### Option 2: Inline in config

Define the colors directly in your `wezterm.lua`:
```lua
local wezterm = require 'wezterm'

local matteblack = {
  colors = {
    background = '#0D0D0D',
    foreground = '#EAEAEA',
    cursor_bg = '#121212',
    cursor_fg = '#F59E0B',
    selection_bg = '#262626',
    selection_fg = '#FFFFFF',
    ansi = {
      '#333333',  -- black
      '#B91C1C',  -- red
      '#059669',  -- green
      '#FBBF24',  -- yellow
      '#3B82F6',  -- blue
      '#8D20B2',  -- magenta
      '#1EA7A0',  -- cyan
      '#EAEAEA',  -- white
    },
    bright = {
      '#8A8A8D',  -- bright black
      '#DC2626',  -- bright red
      '#10B981',  -- bright green
      '#EFBF04',  -- bright yellow
      '#3B82F6',  -- bright blue
      '#B027DE',  -- bright magenta
      '#1EA7A0',  -- bright cyan
      '#FFFFFF',  -- bright white
    },
  },
}

local config = {}

if wezterm.config_builder then
  config = wezterm.config_builder()
end

config.color_schemes = { ['matteblack'] = matteblack }
config.color_scheme = 'matteblack'

return config
```

## Credits

- Original theme: [matteblack.nvim](https://github.com/tahajan/matteblack.nvim) by Taha Nejad
- This is a Wezterm port of the original Neovim colorscheme

## License

MIT License - see [LICENSE](LICENSE) file
