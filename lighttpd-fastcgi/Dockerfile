FROM alpine
MAINTAINER ercas

RUN apk -U add lighttpd php-cgi && \
    sed -ri "s/#   (include \"mod_fastcgi.conf\")/\1/" /etc/lighttpd/lighttpd.conf && \
    sed -i "/root/d" /etc/passwd && \
    sed -i "/root/d" /etc/group && \
    sed -i "/root/d" /etc/shadow

ENTRYPOINT ["/usr/sbin/lighttpd", "-Df", "/etc/lighttpd/lighttpd.conf"]

EXPOSE 80
