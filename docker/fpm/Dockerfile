FROM nextcloud:fpm

## SMB Support
RUN apt-get update && apt-get install -y procps smbclient && rm -rf /var/lib/apt/lists/*

## SUPERVISORD
RUN apt-get update && apt-get install -y \
    supervisor \
  && rm -rf /var/lib/apt/lists/* \
  && mkdir /var/log/supervisord /var/run/supervisord

COPY supervisord.conf /

ENV NEXTCLOUD_UPDATE=0

CMD ["/usr/bin/supervisord", "-c", "/supervisord.conf"]
