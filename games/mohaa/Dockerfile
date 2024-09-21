FROM        ghcr.io/hypernet-org-uk//yolks:debian

LABEL       author="Manuel Dielacher" maintainer="th3dilli@gmx.at"

LABEL       org.opencontainers.image.source="https://github.com/hypernet-org.uk/Custom-Yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN			dpkg --add-architecture i386 \
			&& apt update && apt upgrade -y \
			&& apt install -y lib32gcc-s1 lib32stdc++6 libstdc++5:i386


