ARG ARCH=frommakefile
ARG DISTRIB=frommakefile
ARG DOCKERSRC=frommakefile
ARG USERNAME=frommakefile
#
FROM ${USERNAME}/${DOCKERSRC}:${DISTRIB}_${ARCH}
#
RUN apt-get update && apt-get -y -q install --no-install-recommends git ca-certificates && apt-get clean && rm -rf /var/cache/apt/* /var/lib/apt/lists/*

RUN mkdir -p /opt/sickrage \
    && git clone --depth 1 https://github.com/SickRage/SickRage.git /opt/sickrage

COPY config.ini /opt/sickrage/config.ini

EXPOSE 8081

ENTRYPOINT ["/usr/bin/python", "/opt/sickrage/SickBeard.py"]
