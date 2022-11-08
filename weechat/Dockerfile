FROM ghcr.io/essembeh/alpine

# install packages
RUN apk add --no-cache weechat tzdata ca-certificates 

# add dedicated user
RUN adduser -D -u 1000 weechat
USER weechat

# install omz
ENV ZSH=/home/weechat/.ohmyzsh
RUN CHSH=no RUNZSH=no sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# configure omz
ARG OMZ_THEME="essembeh"
ARG OMZ_PLUGINS="python pip"
RUN zsh -i -c "omz theme set $OMZ_THEME"
RUN zsh -i -c "omz plugin enable $OMZ_PLUGINS"