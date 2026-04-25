FROM ubuntu:24.04

# Install OpenSSH
RUN apt-get update && \
    apt-get install -y --no-install-recommends openssh-server vim markdown && \
    mkdir -p /var/run/sshd && \
    rm -rf /var/lib/apt/lists/*

# User anlegen
RUN useradd -m -s /bin/bash terminal && \
    echo "terminal:terminal" | chpasswd

# SSH Config anpassen
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config && \
    sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin no/' /etc/ssh/sshd_config

COPY ./Readme.md /home/terminal

EXPOSE 22

# SSH im Vordergrund starten
CMD ["/usr/sbin/sshd", "-D"]