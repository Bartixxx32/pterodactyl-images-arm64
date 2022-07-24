FROM        --platform=$TARGETOS/$TARGETARCH node:17-alpine

LABEL       author="Michael Parker" maintainer="parker@pterodactyl.io"

RUN         apk update \
            && apk add ffmpeg \
            && npm -g install npm@latest \
            && useradd -m -d /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
