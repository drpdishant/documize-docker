FROM alpine
ENV documize_ver=v3.4.3
ENV documize_exec=/usr/local/bin/documize
RUN apk add curl && curl -Lo ${documize_exec} https://documize.s3-eu-west-1.amazonaws.com/downloads/documize-community-linux-amd64 && \
    chmod +x ${documize_exec}
COPY config.toml /config.toml
WORKDIR /
CMD documize config.toml
