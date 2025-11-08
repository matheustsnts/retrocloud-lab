FROM alpine:3.19

RUN apk add --no-cache \
    retroarch \
    xvfb \
    x11vnc \
    novnc \
    websockify \
    supervisor \
    mesa-dri-gallium \
    && rm -rf /var/cache/apk/*

WORKDIR /roms

COPY supervisord.conf /etc/supervisord.conf

EXPOSE 8080

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]
