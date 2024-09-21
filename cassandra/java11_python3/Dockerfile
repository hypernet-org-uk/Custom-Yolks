FROM        --platform=$TARGETOS/$TARGETARCH adoptopenjdk/openjdk11:alpine-jre

LABEL       author="Hypernet" maintainer="lezetho@hypernet.org.uk"

LABEL       org.opencontainers.image.source="https://github.com/hypernet-org.uk/Custom-Yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache python3 py3-tz ca-certificates curl fontconfig git openssl sqlite tar tzdata \
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
