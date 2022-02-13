" Disable compatibility with vi which can cause unexpected issues.
set nocompatible
set noswapfile
set relativenumber
set autoread
set hidden
set ruler
set laststatus=2
set autoindent

"netrw autospliting.
let g:netrw_browse_split = 4
let g:netrw_winsize = 80

" Color Column
"set textwidth=210
"set colorcolumn=+1

"forcing purity in vim-life \0/
noremap <Up> <Nop>
noremap <Down> <Nop>
noremap <Left> <Nop>
noremap <Right> <Nop>

"js auto complete.
autocmd FileType javascript set omnifunc=javascriptcomplete#CompleteJS

"colorscheme
colorscheme zellner

" Maintain undo history between sessions
set undofile
set undodir=~/.vim/undodir

"custom switching of split-windows.
nnoremap <C-H> <C-W><C-H>
nnoremap <C-K> <C-W><C-K>
nnoremap <C-L> <C-W><C-L>
nnoremap <C-J> <C-W><C-J>


"custom vim default commands.
nnoremap <C-k> :tabnew 
nnoremap <C-/> :"+y

"vim extension auto-load
autocmd BufNewFile *.html 0r ~/.vim/templates/html.tpl
autocmd BufNewFile *.js 0r ~/.vim/templates/js.tpl


" \0/ \0/ \0/

" Enable type file detection. Vim will be able to try to detect the type of file in use.
filetype on

" Enable plugins and load plugin for the detected file type.
filetype plugin on

" Load an indent file for the detected file type.
filetype indent on
" Turn syntax highlighting on.
syntax on

" Add numbers to each line on the left-hand side.
set number

" Set shift width to 4 spaces.
set shiftwidth=4

" Set tab width to 4 columns.
set tabstop=4

" Use space characters instead of tabs.
set expandtab

" Do not save backup files.
set nobackup

" Do not let cursor scroll below or above N number of lines when scrolling.
set scrolloff=10

" Do not wrap lines. Allow long lines to extend as far as the line goes.
"set nowrap

" While searching though a file incrementally highlight matching characters as you type.
set incsearch

" Ignore capital letters during search.
set ignorecase

" Override the ignorecase option if searching for capital letters.
" This will allow you to search specifically for capital letters.
set smartcase

" Show partial command you type in the last line of the screen.
set showcmd

" Show the mode you are on the last line.
set showmode

" Show matching words during a search.
set showmatch

" Use highlighting when doing a search.
set hlsearch

" Enable auto completion menu after pressing TAB.
set wildmenu

" Make wildmenu behave like similar to Bash completion.
set wildmode=list:longest

" There are certain files that we would never want to edit with Vim.
" Wildmenu will ignore files with these extensions.
set wildignore=*.docx,*.jpg,*.png,*.gif,*.pdf,*.pyc,*.exe,*.flv,*.img,*.xlsx


" Plugins will be downloaded under the specified directory.
call plug#begin(has('nvim') ? stdpath('data') . '/plugged' : '~/.vim/plugged')

" Declare the list of plugins.
Plug 'vim-airline/vim-airline-themes'
Plug 'tpope/vim-sensible'
Plug 'junegunn/seoul256.vim'
Plug 'dense-analysis/ale'
Plug 'preservim/nerdtree'
Plug 'vim-airline/vim-airline'
Plug 'bling/vim-bufferline'
Plug 'sheerun/vim-polyglot'
" List ends here. Plugins become visible to Vim after this call.
let g:javascript_plugin_jsdoc = 1
call plug#end()

" air-line
set guifont=DejaVu\ Sans:s12
let g:airline_powerline_fonts = 1
let g:molokai_original = 1
let g:airline_theme='durant'


if !exists('g:airline_symbols')
    let g:airline_symbols = {}

" unicode symbols
let g:airline_left_sep = '»'
let g:airline_left_sep = '▶'
let g:airline_right_sep = '«'
let g:airline_right_sep = '◀'
let g:airline_symbols.linenr = '␊'
let g:airline_symbols.linenr = '␤'
let g:airline_symbols.linenr = '¶'
let g:airline_symbols.branch = '⎇'
let g:airline_symbols.paste = 'ρ'
let g:airline_symbols.paste = 'Þ'
let g:airline_symbols.paste = '∥'
let g:airline_symbols.whitespace = 'Ξ'
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#left_sep = ' '
let g:airline#extensions#tabline#left_alt_sep = ''
let g:airline#extensions#tabline#formatter = 'unique_tail_improved'


" airline symbols
let g:airline_left_sep = ''
let g:airline_left_alt_sep = ''
let g:airline_right_sep = ''
let g:airline_right_alt_sep = ''
let g:airline_symbols.branch = ''
let g:airline_symbols.readonly = ''
let g:airline_symbols.linenr = ''
endif

"js auto-complete
Plug 'Valloric/YouCompleteMe', { 'do': './install.py --tern-completer' }
" Start autocompletion after 4 chars
let g:ycm_min_num_of_chars_for_completion = 4
let g:ycm_min_num_identifier_candidate_chars = 4
let g:ycm_enable_diagnostic_highlighting = 0
" Don't show YCM's preview window [ I find it really annoying ]
set completeopt-=preview
let g:ycm_add_preview_to_completeopt = 0

