# Author: noraj

# Official verified image
# alpine edge to be able to get i2pd package
FROM alpine:20191114

# Install
RUN apk --no-cache add i2pd --repository http://dl-3.alpinelinux.org/alpine/edge/testing/
# Copy config of i2pd and tunnel config
COPY i2pd.conf tunnels.conf /etc/i2pd/
# Copy the tunnel key to always keep the same b32.i2p address
COPY darkhttpd.dat /var/lib/i2pd/.i2pd/darkhttpd.dat
# fix permissions after copying
RUN chown -R i2pd:i2pd /var/lib/i2pd/.i2pd/

USER i2pd

CMD i2pd --conf=/etc/i2pd/i2pd.conf --tunconf=/etc/i2pd/tunnels.conf