---

layout: inner
title: nvim config
permalink: /vimrc/

---

# Vim / Neovim Configuration file

I think that if my hands get away from the keyboard (e.g. to reach the mouse) is a waste of time, that is why I like vim. Moreover, I would love to be able to navigate everything using some sort of vim interface, nvim has the goal of make any text input in the web be compatible with vim commands, that is why I like nvim. Plus, nvim has better support for inside-vim terminal.

<hr/>
```shell
set nu " Add number to lines


"""""""""""""""""""""""""""""""""""""""""""""""""""
" Config for tabs behaviour
set tabstop=4
set softtabstop=0 noexpandtab "To complete spaces using space and not tab
set shiftwidth=4 "Measurments of the identation

"Enabling this will make the tab key (in insert mode) insert spaces instead of tab characters. This also affects the behavior of the retab command.
set expandtab

"Enabling this will make the tab key (in insert mode) insert spaces or tabs to go to the next indent of the next tabstop when the cursor is at the beginning of a line (i.e. the only preceding characters are whitespace).
set smarttab
""""""""""""""""""""""""""""""""""""""""""""""""""

Plugin 'kien/ctrlp.vim'
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'
Plugin 'valloric/youcompleteme'
Plugin 'tmhedberg/simpylfold'
Plugin 'konfekt/fastfold'
Plugin 'davidhalter/jedi-vim'
Plugin 'scrooloose/syntastic'
Plugin 'tpope/vim-sleuth'
Plugin 'altercation/vim-colors-solarized'

" Natural behaviour for spliting the screen
set splitbelow
set splitright

let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#formatter = 'unique_tail'

set foldmethod=syntax

" ycm setting for compatibility with syntastic and more
let g:ycm_autoclose_preview_window_after_completion = 1
let g:ycm_python_binary_path = 'python'
let g:ycm_show_diagnostics_ui = 0

" Syntactic settings
set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*

let g:syntastic_always_populate_loc_list = 1
let g:syntastic_auto_loc_list = 0
let g:syntastic_check_on_open = 1
let g:syntastic_check_on_wq = 0
let g:syntastic_python_checkers = ['pylint']
let g:syntastic_python_python_exec = 'python'
let g:syntastic_cpp_checkers = ['cpplint']
let g:syntastic_cpp_cpplint_exec = 'cpplint'

let g:syntastic_quiet_messages = {'level': []}
let g:syntastic_cpp_cpplint_args = "--verbose 0"

" For moving between buffers: This is actually not that important
nnoremap <C-O> :redraw!<CR>
nnoremap <C-J> <C-W>j
nnoremap <C-K> <C-W>k
nnoremap <C-L> <C-W>l
nnoremap <C-H> <C-W>h

" Solarized
syntax enable
set background=light
colorscheme solarized

```



<hr/>

## Useful shortcuts

Some of the most useful shortcuts I use in my day to day basis:

#### General

| Command             | Description                                              |
| ------------------- | -------------------------------------------------------- |
| `:ci(`,  `:ci["`    | Change inside (,  Change inside " (not including ( or ") |
| `:da"`, `:da[`      | Delete around ",  Delete around [                        |
| `:e`, `:edit`       | Reload current file                                      |
| `F5` inside `<c-p>` | Reload ctrl+p buffer                                     |
| `<c-o>`, `<c-l>`    | Reload current buffer after detach (ctrl+z)              |
| `:noh`              | Clean find pattern (nvim)                                |



#### Terminal

| Command                  | Description                |
| ------------------------ | -------------------------- |
| `:te`, `:terminal`       | Open terminal (nvim)       |
| `<c-\><c-n>`, `ctrl+\+n` | Get out of terminal (nvim) |



#### Tabs

| Command                    | Description                 |
| -------------------------- | --------------------------- |
| `:tabe [file]`             | Open a new tab              |
| `:tab close`, `:tabclose7` | Close open tab, close tab 7 |
| `:tabonly`                 | Close all other tabs        |
| `gt`                       | Next tab                    |
| `gT`                       | Last tab                    |
| `7gt`                      | Open tab 7                  |