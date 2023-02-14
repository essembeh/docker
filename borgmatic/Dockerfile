FROM ghcr.io/essembeh/debian

# install packages for borgmatic
RUN apt update && \
    apt install -q -y borgbackup openssh-client default-mysql-client python3 python3-pip vim curl wget && \
    apt clean

# install latest version
RUN pip3 install borgmatic 
