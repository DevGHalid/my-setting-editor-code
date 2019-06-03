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
Plug 'SirVer/ultisnips'
Plug 'honza/vim-snippets'
Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
Plug 'airblade/vim-gitgutter'
Plug 'kien/ctrlp.vim'
Plug 'jiangmiao/auto-pairs'
Plug 'mattn/emmet-vim'
Plug 'Valloric/YouCompleteMe'
Plug 'itchyny/lightline.vim'
Plug 'terryma/vim-multiple-cursors'
Plug 'tpope/vim-eunuch'
Plug 'morhetz/gruvbox'
Plug 'digitaltoad/vim-pug'
call plug#end()

set number
set expandtab
set tabstop=2
set shiftwidth=2
set smarttab
set smartindent

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
