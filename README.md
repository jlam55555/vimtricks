# Vim Configuration Sources

## Download Sources

### Appearance
- Syntax Highlighting: [Tomorrow-Night](https://github.com/chriskempson/tomorrow-theme/)

### Airline
- Airline: [Airline](https://github.com/vim-airline/vim-airline) 
- Theme: [Wombat](https://github.com/vim-airline/vim-airline-themes)
- Powerline Font: [Droid Sans Mono (Powerline patch)](https://github.com/powerline/fonts)
- Git Branch: [Fugitive](https://github.com/tpope/vim-fugitive)

### Installer
- Pathogen: [Pathogen](https://github.com/tpope/vim-pathogen)

## Installation

1. **Install Pathogen**

    ```
    mkdir -p ~/.vim/autoload ~/.vim/bundle
    curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
    ```

    Add the following to the `.vimrc`:

    ```
    execute pathogen#infect()
    execute pathogen#helptags()
    ```

2. **Install Airline and Airline Themes (via Pathogen)**

    ```
    cd ~/.vim/bundle
    git clone https://www.github.com/vim-airline/vim-airline
    git clone https://www.github.com/vim-airline/vim-airline-themes
    ``` 

    Add the following to the `.vimrc`:

    ```
    set laststatus=2
    let g:airline_theme='wombat'
    ```

3. **Install Powerline Font**

    ```
    git clone https://www.github.com/powerline/fonts
    ./fonts/install.sh
    rm -rf fonts
    ```

    On xfce-terminal, install font manually via Edit &rarr; Preferences &rarr; Appearance &rarr; Font and select the correct font.
    Add the following to the `.vimrc`:

    ```
    let g:airline_powerline_fonts=1
    ```

4. **Install Fugitive (optional, only for Git users)**

    ```
    cd ~/.vim/bundle
    git clone https://github.com/tpope/vim-fugitive
    vim -u NONE -c "helptags vim-fugitive/doc" -c q
    ```

    Add the following to the `.vimrc`:

    ```
    let g:airline#extensions#hunks#enabled=0
    let g:airline#extensions#branch#enabled=1
    ```

5. **Install the Tommorow-Night theme**

    ```
    mkdir ~/.vim/colors
    git clone https://github.com/chriskempson/tomorrow-theme/
    cd tomorrow-theme/vim/colors
    cp ./* ~/.vim/colors
    cd ../../../
    rm -rf tomorrow-theme
    ```

    Add the following to the `.vimrc`:

    ```
    syntax on
    set t_Co=256
    colorscheme Tomorrow-Night
    ```

6. **Touch up with more customizations to the `.vimrc`**

    ```
    set number        " add line numbers
    set tabstop=2     " make tabs two spaces
    set expandtab     " turns tabs into spaces
    set scrolloff=5   " scroll buffer of five lines
    ```

## Collated Scripts and `.vimrc`

### Scripts:

```
mkdir -p ~/.vim/autoload ~/.vim/bundle
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
cd ~/.vim/bundle
git clone https://www.github.com/vim-airline/vim-airline
git clone https://www.github.com/vim-airline/vim-airline-themes
git clone https://www.github.com/powerline/fonts
./fonts/install.sh
rm -rf fonts
cd ~/.vim/bundle
git clone https://github.com/tpope/vim-fugitive
vim -u NONE -c "helptags vim-fugitive/doc" -c q
mkdir ~/.vim/colors
git clone https://github.com/chriskempson/tomorrow-theme/
cd tomorrow-theme/vim/colors
cp ./* ~/.vim/colors
cd ../../../
rm -rf tomorrow-theme
```

### `.vimrc`:

```
set number
set tabstop=2
set shiftwidth=2
set expandtab
syntax on
set t_Co=256
colorscheme Tomorrow-Night
set scrolloff=5
set laststatus=2
execute pathogen#infect()
execute pathogen#helptags()
let g:airline_powerline_fonts=1
let g:airline_theme='wombat'
let g:airline#extensions#hunks#enabled=0
let g:airline#extensions#branch#enabled=1
```
