FROM        --platform=$TARGETOS/$TARGETARCH node:17-alpine

LABEL       author="Michael Parker" maintainer="parker@pterodactyl.io"

RUN         apk add --update --no-cache ffmpeg ca-certificates tzdata \
                && adduser -D -h /home/container container
RUN apk add --no-cache libgcc libstdc++ curl ca-certificates
USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]