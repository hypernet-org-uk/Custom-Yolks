FROM        --platform=$TARGETOS/$TARGETARCH erlang:22-alpine

LABEL       author="Hypernet" maintainer="lezetho@hypernet.org.uk"

LABEL       org.opencontainers.image.source="https://github.com/hypernet-org.uk/Custom-Yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache ca-certificates curl git openssl sqlite tar tzdata iproute2 \
				&& adduser -D -h /home/container container \
				&& rm -rf /usr/bin/dd \
				&& rm -rf /usr/bin/fallocate \
				&& rm -rf /usr/bin/truncate \
				&& rm -rf /usr/bin/xfs_mkfile

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
