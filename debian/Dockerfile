FROM debian:stable-slim

# default theme
ARG OMZ_THEME="essembeh"
# default plugins
ARG OMZ_PLUGINS="git python pip"


# install dependencies
RUN apt update && \
    apt install -y zsh git curl vim tmux && \
    apt clean

# install ohmyzsh
ENV ZSH=/root/.ohmyzsh
RUN CHSH=no RUNZSH=no sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# set ohmyzsh theme
RUN zsh -i -c "omz theme set $OMZ_THEME"
# enable ohmyzsh plugins
RUN zsh -i -c "omz plugin enable $OMZ_PLUGINS"
# disable ohmyzsh auto update
RUN zsh -i -c "zstyle ':omz:update' mode disabled"

# configure tmux
ADD https://raw.githubusercontent.com/essembeh/dotfiles/main/tmux/tmux.conf /etc/tmux.conf
RUN chmod 644 /etc/tmux.conf

# configure vim
RUN echo "set mouse-=a" > /root/.vimrc
