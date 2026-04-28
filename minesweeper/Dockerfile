FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    gnome-mines \
    xrdp \
    xorgxrdp \
    dbus-x11 \
    && apt-get clean

RUN useradd -ms /bin/bash terminal && \
    echo "terminal:terminal" | chpasswd

RUN echo "gnome-mines" > /home/terminal/.xsession && \
    chown terminal:terminal /home/terminal/.xsession

EXPOSE 3389

CMD ["/bin/bash", "-c", "/usr/sbin/xrdp-sesman & exec /usr/sbin/xrdp --nodaemon"]