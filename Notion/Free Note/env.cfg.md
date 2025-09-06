---
Chủ đề:
---
```Plain
#!/bin/sh

# Clipboard syn
sudo apt-get install xclip

# ------------------------------------------------------------------------------------------------------------------------------------------------ #
# Terminal tools

# Install fuzy finder
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
find * -type f | fzf > selected
source <(fzf --zsh)

# Tmux
sudo apt-get tmux
# Tmux Prefix
# Source :https://github.com/gpakosz/.tmux
cd
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local

\#Jump
wget https://github.com/gsamokovarov/jump/releases/download/v0.30.1/jump_0.30.1_amd64.deb && sudo dpkg -i jump_0.30.1_amd64.deb



# ------------------------------------------------------------------------------------------------------------------------------------------------ #
# Oh my zsh Block

# Oh-my-zsh
sh -c "$(curl -fsSLhttps://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# PowerLevel9k Theme
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k

# Nerd Font
https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/Hack/Regular/complete/Hack%20Regular%20Nerd%20Font%20Complete.ttf
# Download and install Font
# Set font in reference's terminal

# Zsh autosuggestion
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
tmux source ~/.tmux.conf
# ------------------------------------------------------------------------------------------------------------------------------------------------ #



# ------------------------------------------------------------------------------------------------------------------------------------------------ #
# Vim-Plugins
plugins=(
  git
  vi-mode
  zsh-autosuggestions
)
bindkey '^ ' autosuggest-accept


# Vim-plug plugins manager
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
# ------------------------------------------------------------------------------------------------------------------------------------------------ #



# ------------------------------------------------------------------------------------------------------------------------------------------------ #
# Switch CapsLock vs ESC
sudo apt-get install gnome-tweak-tool
# Goto tweak app -> keyboard & mouse -> Additional Layout Options -> Caps Lock Behavior -> Swap ESC and Caps Lock
```