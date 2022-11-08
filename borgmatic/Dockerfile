FROM ghcr.io/essembeh/debian

RUN apt update && \
    apt install -q -y borgbackup openssh-client default-mysql-client python3 python3-pip vim curl wget && \
    apt clean && \
    pip3 install borgmatic 
