FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    xrdp \
    xorgxrdp \
    dbus-x11 \
    firefox \
    nginx \
    locales \
    && locale-gen de_DE.UTF-8 \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

ENV LANG=de_DE.UTF-8
ENV LC_ALL=de_DE.UTF-8
ENV LANGUAGE=de_DE:de

RUN useradd -ms /bin/bash terminal && \
    echo "terminal:terminal" | chpasswd

COPY index.html /usr/share/nginx/html/
COPY style.css /usr/share/nginx/html/
COPY js.js /usr/share/nginx/html/

RUN echo "exec firefox --kiosk http://localhost" > /home/terminal/.xsession && \
    chown terminal:terminal /home/terminal/.xsession

EXPOSE 3389 80

CMD ["bash", "-c", "nginx -g 'daemon off;' & exec /usr/sbin/xrdp --nodaemon"]