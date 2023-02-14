FROM ghcr.io/essembeh/alpine

# install packages
RUN apk add --no-cache weechat tzdata ca-certificates

# add dedicated user
RUN adduser -D -u 1000 weechat
USER weechat

# install ohmyzsh
ENV ZSH=/home/weechat/.ohmyzsh
RUN CHSH=no RUNZSH=no sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# ohmyzsh config
RUN zsh -i -c "omz theme set essembeh"
RUN zsh -i -c "omz plugin enable extract"
RUN zsh -i -c "zstyle ':omz:update' mode disabled"
