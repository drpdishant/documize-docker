FROM scratch
ADD alpine-minirootfs-3.14.0-x86_64.tar.gz /
LABEL project.name="Documize"
LABEL project.url="documize.com"
LABEL image.maintainer="Dishant Pandya"
LABEL maintainer.email="drpdishant@gmail.com"
LABEL version="1.0"
LABEL description="Team-driven content authoring & automation for secure internal and external documentation."
ENV documize_ver=v3.9.0
ENV documize_exec=/usr/local/bin/documize
RUN apk add curl && curl -Lo ${documize_exec} https://github.com/documize/community/releases/download/${documize_ver}/documize-community-linux-amd64 && \
    chmod +x ${documize_exec}
COPY config.toml /config.toml
WORKDIR /
CMD documize config.toml
HEALTHCHECK CMD curl --fail http://localhost:5001/ || exit 1
