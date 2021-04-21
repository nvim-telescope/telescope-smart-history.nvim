# telescope-smart-history.nvim

A history implementation that memorizes prompt input for a specific context.
This means that each prompt input is assosiated with a calling picker and cwd.

So if you work on multiple projects and cycle back it will only show input that
was used in this Project.

## Setup

It requires [sql.nvim](https://github.com/tami5/sql.nvim), because its easier
and faster than having a flat text file that keeps track of input + picker + cwd.

It will be configured with the same keys as the normal history configuration.

```lua
telescope.setup {
  defaults = {
    history_location = '~/.local/share/nvim/databases/telescope_history.sqlite3',
    -- For this history limit is sensitive to the context.
    -- So limit 100 for picker `x` with cwd `y`
    history_limit = 100,
  }
}


require('telescope').load_extension('smart_history')
```
