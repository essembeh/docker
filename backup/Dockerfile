FROM ghcr.io/essembeh/debian

# install packages for borgmatic
RUN apt update && \
    apt install -q -y \
        openssh-client default-mysql-client rsync \
        python3 python3-pip \
        borgbackup restic && \
    apt clean

# install pipx
RUN pip3 install pipx

# install borgmatic latest version
RUN pip3 install borgmatic
