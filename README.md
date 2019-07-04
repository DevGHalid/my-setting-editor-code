# My-setting-editorCode
My setting editor code



<h1>Setting vscode</h1>

<p>
{
    "window.zoomLevel": 2,
    "editor.fontSize": 17,
    "editor.fontFamily": "",
    "window.menuBarVisibility": "toggle",
    "editor.tabSize": 2,
    "prettier.singleQuote": true,
    "prettier.tabWidth": 2,
    "editor.wordWrap": "on",
    "editor.minimap.enabled": false,
    "zenMode.hideTabs": false,
    "terminal.integrated.rendererType": "dom",
    "editor.formatOnSave": true,
    "flow.useNPMPackagedFlow": true,
    "javascript.validate.enable": false,
    "workbench.colorTheme": "Webstorm IntelliJ Darcula Theme"
    // "editor.renderIndentGuides": false,
}
</p>

<hr />

<h1>Setting vim</h1>

<p>
   "plug
call plug#begin()
Plug 'SirVer/ultisnips'
Plug 'honza/vim-snippets'
Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
Plug 'airblade/vim-gitgutter'
Plug 'kien/ctrlp.vim'
Plug 'jiangmiao/auto-pairs'
Plug 'mattn/emmet-vim'
Plug 'itchyny/lightline.vim'
Plug 'terryma/vim-multiple-cursors'
Plug 'tpope/vim-eunuch'
Plug 'digitaltoad/vim-pug'
Plug 'alvan/vim-closetag'
Plug 'prettier/vim-prettier', {
  \ 'do': 'yarn install',
  \ 'for': ['javascript', 'typescript', 'css', 'less', 'scss', 'json', 'graphql', 'markdown', 'vue', 'yaml', 'html'] }
Plug 'leafgarland/typescript-vim'
Plug 'mxw/vim-jsx'
Plug 'burner/vim-svelte'
Plug 'posva/vim-vue'

if has('nvim')
  Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
else
  Plug 'Shougo/deoplete.nvim'
  Plug 'roxma/nvim-yarp'
  Plug 'roxma/vim-hug-neovim-rpc'
endif

"themes
"Plug 'NLKNguyen/papercolor-theme'
Plug 'arcticicestudio/nord-vim'
"Plug 'altercation/vim-colors-solarized'

call plug#end()

colorscheme nord 
"let g:solarized_termcolors=256
"colorscheme jellybeans

"set background=dark
"colorscheme solarized

"let
let g:closetag_filenames = '*.html,*.xml,*.php,*.js,*.ejs,*.jsx,*.ts,*.tsx,*.vue'
let g:prettier#exec_cmd_async = 1
let g:deoplete#enable_at_startup = 1

"emmet
let g:user_emmet_leader_key='<C-Z>'

"set
set number
set expandtab
set tabstop=2
set shiftwidth=2
set smarttab
set smartindent

"map
map <C-e> :NERDTreeToggle<CR>

map <silent> <C-h> :call WinMove("h")<CR>
map <silent> <C-j> :call WinMove("j")<CR>
map <silent> <C-k> :call WinMove("k")<CR>
map <silent> <C-l> :call WinMove("l")<CR>

function! WinMove(key)
  let t:curwin = winnr()
  exec "wincmd ".a:key
  if (t:curwin == winnr())
    if (match(a:key, '[jk]'))
      wincmd v
    else
      wincmd s
    endif
    exec "wincmd ".a:key
  endif
endfunction

execute pathogen#infect()
set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*

let g:syntastic_always_populate_loc_list = 1
let g:syntastic_auto_loc_list = 1
let g:syntastic_check_on_open = 1
let g:syntastic_check_on_wq = 0

</p>
