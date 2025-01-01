# VIM 配置说明

## 地址
`~/.config/nvim/init.vim`

## 插件

### [github/copilot.vim](https://github.com/github/copilot.vim)

用于代码智能提示

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

### [mg979/vim-visual-multi](https://github.com/mg979/vim-visual-multi)

增加多选插件

```vim
Plug 'mg979/vim-visual-multi', {'branch': 'master'}
```

| Key |	Action |
| :---: | :----: |
| n	| find next (same as C-n)                              |
| N | find previous                                        |
| ] |	goto next                                            |
| [ |	goto previous                                        |
| q |	skip and go to next                                  |
| Q |	remove region                                        |
| C-f |	fast forward (go to first region in next page)     |
| C-b |	fast backward (go to first region in previous page)|

### [vim-surround](https://github.com/tpope/vim-surround)

**左括号有空格，右括号无空格**

`Hello world!`

Now with the cursor on "Hello", press ysiw] (iw is a text object). 

`[Hello] world!`

cs["

`"Hello" world!`

ds"

`Hello world!`

ys2w"

`"Hello world"!`

## [im-select](https://github.com/daipeihust/im-select)

退出 insert 模式下，自动切换到苹果的输入法

1. 安装命令行工具 im-select。 GitHub - daipeihust/im-select: Switch your input method through terminal

```bash
brew tap daipeihust/tap && brew install im-select
```
2. vim 配置增加如下配置 (先用 im-select 命令看一下你的默认输入法，下边改成你的)

```bash
autocmd InsertLeave * :silent !/usr/local/bin/im-select com.apple.keylayout.ABC
```
