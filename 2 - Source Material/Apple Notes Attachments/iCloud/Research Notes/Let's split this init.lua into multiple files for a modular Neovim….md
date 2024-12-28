## **Folder Structure**
~/.config/nvim/
│
├── init.lua
└── lua/
    ├── core/
    │   ├── options.lua
    │   ├── keymaps.lua
    │   └── autocommands.lua
    └── plugins/
        ├── init.lua
        ├── lazy.lua
        ├── lsp.lua
        └── telescope.lua

## **1. init.lua (root)**
Modify init.lua to load other modules:
-- Set leader key early
vim.g.mapleader = ' '
vim.g.maplocalleader = ' '

-- Core configurations
require('core.options')
require('core.keymaps')
require('core.autocommands')

-- Plugin configurations
require('plugins.init')

## **2. lua/core/options.lua**
Extract general settings here:
vim.opt.number = true
vim.opt.relativenumber = true
vim.opt.mouse = 'a'
vim.opt.showmode = false
vim.opt.breakindent = true
vim.opt.undofile = true
vim.opt.ignorecase = true
vim.opt.smartcase = true
vim.opt.signcolumn = 'yes'
vim.opt.updatetime = 250
vim.opt.timeoutlen = 300
vim.opt.splitright = true
vim.opt.splitbelow = true
vim.opt.list = true
vim.opt.listchars = { tab = '» ', trail = '·', nbsp = '␣' }
vim.opt.inccommand = 'split'
vim.opt.cursorline = true
vim.opt.scrolloff = 10

## **3. lua/core/keymaps.lua**
Extract key mappings:
vim.keymap.set('n', '<Esc>', '<cmd>nohlsearch<CR>')
vim.keymap.set('n', '<leader>q', vim.diagnostic.setloclist, { desc = 'Open diagnostic [Q]uickfix list' })
vim.keymap.set('t', '<Esc><Esc>', '<C-\\><C-n>', { desc = 'Exit terminal mode' })
vim.keymap.set('i', '<C-h>', '<Left>', { noremap = false, silent = true })
vim.keymap.set('i', '<C-j>', '<Down>', { noremap = false, silent = true })
vim.keymap.set('i', '<C-k>', '<Up>', { noremap = false, silent = true })
vim.keymap.set('i', '<C-l>', '<Right>', { noremap = false, silent = true })
vim.keymap.set('i', '<C-f>', '<C-x><C-f>', { noremap = true, silent = true })
vim.keymap.set('n', '<leader>ll', ':setlocal spell spelllang=en_us<CR>')

## **4. lua/core/autocommands.lua**
Extract autocommands:
vim.api.nvim_create_autocmd('TextYankPost', {
    desc = 'Highlight when yanking (copying) text',
    group = vim.api.nvim_create_augroup('kickstart-highlight-yank', { clear = true }),
    callback = function()
        vim.highlight.on_yank()
    end,
})

## **5. lua/plugins/init.lua**
This will load all plugin configurations:
require('plugins.lazy')
require('plugins.lsp')
require('plugins.telescope')

## **6. lua/plugins/lazy.lua**
Plugin manager (lazy.nvim) configuration:
local lazypath = vim.fn.stdpath 'data' .. '/lazy/lazy.nvim'
if not (vim.uv or vim.loop).fs_stat(lazypath) then
    vim.fn.system { 'git', 'clone', '--branch=stable', 'https://github.com/folke/lazy.nvim', lazypath }
end
vim.opt.rtp:prepend(lazypath)

require('lazy').setup({
    'tpope/vim-sleuth',
    {
        'lewis6991/gitsigns.nvim',
        opts = { signs = { add = '+', change = '~', delete = '_' } },
    },
    { 'windwp/nvim-autopairs', event = 'InsertEnter', config = true },
    { 'xiyaowong/transparent.nvim', lazy = false },
})

## **7. lua/plugins/lsp.lua**
LSP configuration extracted here:
require('neovim/nvim-lspconfig')
vim.api.nvim_create_autocmd('LspAttach', {
    group = vim.api.nvim_create_augroup('kickstart-lsp-attach', { clear = true }),
    callback = function(event)
        vim.keymap.set('n', 'gd', vim.lsp.buf.definition, { buffer = event.buf })
    end,
})

## **8. lua/plugins/telescope.lua**
Telescope setup:
require('telescope').setup {
    extensions = {
        ['ui-select'] = {
            require('telescope.themes').get_dropdown(),
        },
    },
}

Would you like the complete files generated or any further customization?