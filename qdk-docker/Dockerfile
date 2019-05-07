FROM ubuntu:18.04

COPY QDK /root/QDK
WORKDIR /root/QDK
RUN ./InstallToUbuntu.sh install && \
	apt update && \
	apt install -y rsync && \
        apt install -y git && \
	apt-get remove --purge -yq && \
    apt-get autoclean -y && \
    apt-get autoremove -y && \
    mkdir -p /go/src/github.com/qeek-dev && \
    rm -f /root/QDK/shared/template/shared/init.sh && \
    rm -rf /var/lib/{cache,log}/ && \
    rm -rf /var/lib/apt/lists/*.lz4 && \
    rm -rf /tmp/* /var/tmp/* && \
    rm -rf /usr/share/doc/ && \
    rm -rf /usr/share/man/

ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/QDK/bin
CMD ["/bin/bash"]
