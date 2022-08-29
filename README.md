# NeoVim Config

Make NeoVim best IDE

## Installation

You need to install `vim-plug` first before using this config.

Read and follow the instructions here: https://github.com/junegunn/vim-plug

After that you can create `nvim` folder in `~/.config`, then git clone this repo!

Later you can run `:PlugInstall` to install all the dependencies.

## Customize

### Bufferline

Remove `force = true` to make unsaved buffer not force close.

**Path** `lua/bufferline/commands.lua`

**Before**
```lua
local function delete_element(id)
  if config:is_tabline() then
    vim.cmd("tabclose " .. id)
  else
    api.nvim_buf_delete(id, { force = true })
  end
end
```

**After**
```lua
local function delete_element(id)
  if config:is_tabline() then
    vim.cmd("tabclose " .. id)
  else
    api.nvim_buf_delete(id, {})
  end
end
```
