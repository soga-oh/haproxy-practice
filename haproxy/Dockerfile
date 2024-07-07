FROM almalinux:9

RUN dnf install -y epel-release && \
    dnf install -y haproxy keepalived && \
    dnf clean all

COPY haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg

CMD ["sh", "-c", "haproxy -f /usr/local/etc/haproxy/haproxy.cfg & keepalived -n -D"]
