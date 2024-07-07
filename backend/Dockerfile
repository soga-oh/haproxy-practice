FROM almalinux:9

RUN dnf install -y httpd && \
    dnf clean all

COPY httpd.conf /etc/httpd/conf/httpd.conf
COPY index.html /var/www/html/index.html

EXPOSE 80

CMD ["httpd", "-D", "FOREGROUND"]
