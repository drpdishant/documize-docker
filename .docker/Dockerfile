FROM alpine
LABEL project.name="Documize"
LABEL project.url="documize.com"
LABEL image.maintainer="Dishant Pandya"
LABEL maintainer.email="drpdishant@gmail.com"
LABEL version="1.0"
LABEL description="Team-driven content authoring & automation for secure internal and external documentation."
ENV documize_ver=v3.8.1
ENV documize_exec=/usr/local/bin/documize
RUN apk add curl && curl -Lo ${documize_exec} https://documize.s3-eu-west-1.amazonaws.com/downloads/documize-community-linux-amd64 && \
    chmod +x ${documize_exec}
COPY config.toml /config.toml
WORKDIR /
CMD documize config.toml
HEALTHCHECK CMD curl --fail http://localhost:5001/ || exit 1
