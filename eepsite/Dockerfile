# Author: noraj

# Official verified image
FROM alpine:3.10

RUN apk --no-cache add darkhttpd
COPY website /var/www/localhost/htdocs/

USER darkhttpd

CMD darkhttpd /var/www/localhost/htdocs/ --port 8080 --no-server-id --no-listing