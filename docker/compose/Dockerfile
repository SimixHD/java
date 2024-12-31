FROM        --platform=$TARGETOS/$TARGETARCH debian:stable-slim

LABEL       org.opencontainers.image.source="https://github.com/SimixHD/java"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache ca-certificates tzdata \
		&& curl -L "https://github.com/docker/compose/releases/download/2.32.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose \
  		&& chmod +x /usr/local/bin/docker-compose \
		&& adduser -D -h /home/container container
  	

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
