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
call plug#begin()
Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
Plug 'airblade/vim-gitgutter'
Plug 'kien/ctrlp.vim'
Plug 'jiangmiao/auto-pairs'
Plug 'mattn/emmet-vim'
Plug 'itchyny/lightline.vim'

Plug 'terryma/vim-multiple-cursors'
Plug 'digitaltoad/vim-pug'
Plug 'alvan/vim-closetag'
Plug 'leafgarland/typescript-vim'

"plugin commentary - gc
Plug 'tpope/vim-commentary'

"linter
Plug 'w0rp/ale'

"autocomplete
Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }

"themes
Plug 'arcticicestudio/nord-vim'

"js
Plug 'prettier/vim-prettier', {
  \ 'do': 'yarn install',
  \ 'for': ['javascript', 'typescript', 'css', 'less', 'scss', 'json', 'graphql', 'vue', 'html'] }
Plug 'mustache/vim-mustache-handlebars'
Plug 'mxw/vim-jsx'
Plug 'posva/vim-vue'

call plug#end()

colorscheme nord 

"let
let g:closetag_filenames = '*.html,*.xml,*.php,*.js,*.ejs,*.jsx,*.tsx,*.vue'
let g:prettier#exec_cmd_async = 1
let g:deoplete#enable_at_startup = 1

"linter
let g:ale_fixers = {'javascript': ['eslint']}
let g:ale_sign_error = '>>'
let g:ale_sign_warning = '>>'
let g:ale_fix_on_save = 1

let b:ale_linters = ['flake8', 'pylint']

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
</p>
