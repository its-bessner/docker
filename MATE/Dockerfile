FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    mate-desktop-environment-core \
    xrdp xorgxrdp dbus-x11 \
    locales language-pack-de \
    && locale-gen de_DE.UTF-8 \
    && update-locale LANG=de_DE.UTF-8 \
    && apt-get clean

ENV LANG=de_DE.UTF-8
ENV LC_ALL=de_DE.UTF-8
ENV LANGUAGE=de_DE:de

RUN useradd -ms /bin/bash terminal && \
    echo "terminal:terminal" | chpasswd

RUN echo "mate-session" > /home/terminal/.xsession && \
    chown terminal:terminal /home/terminal/.xsession

EXPOSE 3389

CMD ["/bin/bash", "-c", "/usr/sbin/xrdp-sesman --nodaemon & exec /usr/sbin/xrdp --nodaemon"]