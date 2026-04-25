FROM debian:stable-slim

RUN apt-get update \
 && apt-get install -y vim curl \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace

CMD ["bash"]
