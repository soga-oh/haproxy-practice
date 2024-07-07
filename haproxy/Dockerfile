FROM almalinux:9

RUN dnf install -y epel-release && \
    dnf install -y haproxy keepalived net-tools iproute procps-ng && \
    dnf clean all

COPY haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg

#CMD ["sh", "-c", "haproxy -f /usr/local/etc/haproxy/haproxy.cfg & keepalived -n -D"]

# 仮想IPアドレスのバインディングを許可
RUN echo "net.ipv4.ip_nonlocal_bind = 1" >> /etc/sysctl.conf

CMD ["sh", "-c", "sysctl -p && haproxy -f /usr/local/etc/haproxy/haproxy.cfg & keepalived -n -D"]

