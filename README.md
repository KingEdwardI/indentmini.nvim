# indentmini.nvim
A minimal and blazing fast indentline plugin by using `nvim_set_decoration_provide` api

## Install

- Lazy.nvim

```lua
require('lazy').setup({
    'nvimdev/indentmini.nvim',
    event = 'BufEnter',
    config = function()
        require('indentmini').setup()
    end,
})
```

## Config

- char     -- string type default is  `│`,
- exclude  -- table  type add exclude filetype in this table

```lua
config = function()
    require("indentmini").setup({
        char = "|",
        exclude = {
            "erlang",
            "markdown",
        }
    })

    -- For colored indent markers, you'll have to define exactly 6 colors to use
    vim.cmd.highlight('IndentLine1 guifg=#123456')
    vim.cmd.highlight('IndentLine2 guifg=#ABCDEF')
    vim.cmd.highlight('IndentLine3 guifg=#1A2B3C')
    vim.cmd.highlight('IndentLine4 guifg=#32a852')
    vim.cmd.highlight('IndentLine5 guifg=#420690')
    vim.cmd.highlight('IndentLine6 guifg=#999999')

    -- if you want fewer than 6, you'll have to re-define the ones you want.
    -- vim.cmd.highlight('IndentLine1 guifg=#123456')
    -- vim.cmd.highlight('IndentLine2 guifg=#ABCDEF')
    -- vim.cmd.highlight('IndentLine3 guifg=#1A2B3C')
    -- vim.cmd.highlight('IndentLine1 guifg=#123456')
    -- vim.cmd.highlight('IndentLine2 guifg=#ABCDEF')
    -- vim.cmd.highlight('IndentLine3 guifg=#1A2B3C')
end,
```

## License MIT
