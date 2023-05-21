# VIM 配置说明

## copilot

github copilot 插件用于代码提示

```vim
Plug 'github/copilot.vim'

" ==================== copilot.nvim ====================
" 通过设置全局变量启用 Copilot 插件
let g:copilot_enabled = 1

" 将 leader 键后跟 "go" 映射到 :Copilot 命令，该命令基于当前上下文生成代码建议。
nnoremap <silent> <leader>go :Copilot<CR>

将 leader 键后跟 "ge" 映射到 :Copilot enable 命令，如果 Copilot 插件已禁用，则启用它。
nnoremap <silent> <leader>ge :Copilot enable<CR>

将 leader 键后跟 "gd" 映射到 :Copilot disable 命令，如果 Copilot 插件已启用，则禁用它。
nnoremap <silent> <leader>gd :Copilot disable<CR>

本来是将 Ctrl-P 映射到 Copilot 的 suggest 命令上
" inoremap <c-p> <Plug>(copilot-suggest)

将 Ctrl-C 组合键映射到接受当前代码建议的命令上。
imap <silent><script><expr> <C-C> copilot#Accept("")

禁用代码建议选择的默认 tab 键映射。
let g:copilot_no_tab_map = v:true

将 Ctrl-N 映射到选择下一个代码建议的命令上。
inoremap <c-n> <Plug>(copilot-next)

将 Ctrl-L 映射到选择上一个代码建议的命令上。
inoremap <c-l> <Plug>(copilot-previous)

```

## mg979/vim-visual-multi

增加多选插件

```vim
Plug 'mg979/vim-visual-multi', {'branch': 'master'}
```

| Key |	Action |
| :---: | :----|
| n	| find next (same as C-n)                              |
| N | find previous                                        |
| ] |	goto next                                            |
| [ |	goto previous                                        |
| q |	skip and go to next                                  |
| Q |	remove region                                        |
| C-f |	fast forward (go to first region in next page)     |
| C-b |	fast backward (go to first region in previous page)|


