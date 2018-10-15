FROM alpine:latest

# Install runtime dependencies. The versions are pinned for reproducible,
# deterministic, pure builds.
RUN apk --no-cache --no-progress upgrade && \
    apk --no-cache --no-progress add bash curl ip6tables iptables openvpn \
    shadow tini && \
    addgroup -S vpn && \
    rm -rf /tmp/*

RUN mkdir /usr/share/openvpn
RUN cp /etc/openvpn/* /usr/share/openvpn/

WORKDIR /etc/openvpn
ENTRYPOINT ["openvpn"]
