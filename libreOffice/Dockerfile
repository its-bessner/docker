FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    libreoffice \
    libreoffice-gtk3 \
    xrdp xorgxrdp dbus-x11 \
    locales \
    && locale-gen de_DE.UTF-8 \
    && apt-get clean

ENV LANG=de_DE.UTF-8
ENV LC_ALL=de_DE.UTF-8
ENV LANGUAGE=de_DE:de

RUN useradd -ms /bin/bash terminal && \
    echo "terminal:terminal" | chpasswd

# direkt LibreOffice starten
RUN echo "libreoffice --writer" > /home/terminal/.xsession && \
    chown terminal:terminal /home/terminal/.xsession

EXPOSE 3389

CMD /bin/bash -c "/usr/sbin/xrdp-sesman --nodaemon & exec /usr/sbin/xrdp --nodaemon"