# Use the official Azul Platform Prime Ubuntu image
FROM azul/prime-ubuntu:21

# Set maintainer info
LABEL author="Energit" maintainer="energitmain@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies required for Pterodactyl and common Minecraft tools
RUN apt-get update && \
    apt-get install -y curl ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 && \
    useradd -d /home/container -m container

# Set environment variables for the container
USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

# Copy the entrypoint script into the container
COPY ./entrypoint.sh /entrypoint.sh
CMD ["/bin/bash", "/entrypoint.sh"]
