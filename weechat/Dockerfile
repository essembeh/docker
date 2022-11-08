FROM ghcr.io/essembeh/alpine

# install packages
RUN apk add --no-cache weechat tzdata ca-certificates 

# add dedicated user
RUN adduser -D -u 1000 weechat
USER weechat
