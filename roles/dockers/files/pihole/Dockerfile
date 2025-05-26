FROM alpinelinux/unbound

# Copy the local unbound-config directory to /etc/unbound in the container
RUN mkdir -p /etc/unbound

# Expose the necessary ports (e.g., 53 for DNS)
EXPOSE 5335/udp
EXPOSE 5335/tcp

# Install the dig app
RUN apk add --no-cache bind-tools
# #get the root hints
# RUN unbound-anchor -a /etc/unbound/root.key

# get the named cache
ADD https://www.internic.net/domain/named.cache /etc/unbound/root.hints
COPY ./unbound/config/ /etc/unbound/

# Mount point for /etc/unbound
VOLUME /etc/unbound
VOLUME /var/log/unbound
VOLUME /assets/unbound

# Start unbound in the foreground
CMD ["unbound", "-d"]
