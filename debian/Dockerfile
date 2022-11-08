FROM debian:stable-slim

# install dependencies
RUN apt update && \
    apt install -y zsh git curl vim tmux && \
    apt clean

# install omz
ENV ZSH=/root/.oh-my-zsh
RUN CHSH=no RUNZSH=no sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# configure omz
ARG OMZ_THEME="essembeh"
ARG OMZ_PLUGINS="python pip"
RUN zsh -i -c "omz theme set $OMZ_THEME"
RUN zsh -i -c "omz plugin enable $OMZ_PLUGINS"

# configure tmux
ADD https://raw.githubusercontent.com/essembeh/dotfiles/main/tmux/tmux.conf /root/.tmux.conf

# configure vim
RUN echo "set mouse-=a" > /root/.vimrc
