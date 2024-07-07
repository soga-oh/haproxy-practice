FROM almalinux:9

RUN dnf install -y httpd && \
    dnf clean all

COPY httpd.conf /etc/httpd/conf/httpd.conf

EXPOSE 80

CMD ["httpd", "-D", "FOREGROUND"]
