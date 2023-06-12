FROM ghcr.io/essembeh/debian

RUN apt update 
# install backup tools
RUN apt install -q -y borgbackup borgmatic restic
# install external tools for borgmatic
RUN apt install -q -y openssh-client default-mysql-client rsync 
