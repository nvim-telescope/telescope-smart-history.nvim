# telescope-smart-history.nvim

A history implementation that memorizes prompt input for a specific context.
This means that each prompt input is associated with a calling picker and cwd.

So if you work on multiple projects and cycle back it will only show input that
was used in this Project.

## Setup

It requires [sqlite.lua](https://github.com/tami5/sqlite.lua), because its easier
and faster than having a flat text file that keeps track of input + picker + cwd.

It will be configured with the same keys as the normal history configuration.

```lua
telescope.setup {
  defaults = {
    history = {
      path = '~/.local/share/nvim/databases/telescope_history.sqlite3',
      limit = 100,
    }
  }
}


require('telescope').load_extension('smart_history')
```
