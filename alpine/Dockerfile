FROM alpine:latest

# install dependencies
RUN apk add --no-cache zsh git curl vim tmux

# install omz
ENV ZSH=/root/.oh-my-zsh
RUN CHSH=no RUNZSH=no sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# configure omz
ARG OMZ_THEME="essembeh"
ARG OMZ_PLUGINS="python pip"
RUN zsh -i -c "omz theme set $OMZ_THEME"
RUN zsh -i -c "omz plugin enable $OMZ_PLUGINS"

# configure tmux
ADD https://raw.githubusercontent.com/essembeh/dotfiles/main/tmux/tmux.conf /etc/tmux.conf
RUN chmod 644 /etc/tmux.conf

# configure vim
RUN echo "set mouse-=a" > /root/.vimrc
