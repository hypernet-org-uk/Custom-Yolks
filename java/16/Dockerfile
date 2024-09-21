FROM        --platform=$TARGETOS/$TARGETARCH eclipse-temurin:16-jdk-focal

LABEL       author="Hypernet" maintainer="lezetho@hypernet.org.uk"

LABEL       org.opencontainers.image.source="https://github.com/hypernet-org.uk/Custom-Yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update -y \
            && apt install -y \
                curl \
                lsof \
                ca-certificates \
                openssl \
                git \
                tar \
                sqlite3 \
                fontconfig \
                tzdata \
                iproute2 \
                libfreetype6 \
                tini \
				zip \
				unzip \
                && rm -rf /usr/bin/dd \
                && rm -rf /usr/bin/fallocate \
                && rm -rf /usr/bin/truncate \
                && rm -rf /usr/bin/xfs_mkfile

## Setup user and working directory
RUN         useradd -m -d /home/container -s /bin/bash container
USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

STOPSIGNAL SIGINT

COPY        --chown=container:container ./../entrypoint.sh /entrypoint.sh
RUN         chmod +x /entrypoint.sh
ENTRYPOINT    ["/usr/bin/tini", "-g", "--"]
CMD         ["/entrypoint.sh"]
