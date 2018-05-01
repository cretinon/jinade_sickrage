ARG ARCH=frommakefile
ARG DISTRIB=frommakefile
ARG DOCKERSRC=frommakefile
ARG USERNAME=frommakefile
#
FROM ${USERNAME}/${DOCKERSRC}:${DISTRIB}_${ARCH}
#
RUN apk add --no-cache --purge git ca-certificates && rm -rf /var/cache/apk/* 

RUN mkdir -p /opt/sickrage \
    && git clone --depth 1 https://github.com/SickRage/SickRage.git /opt/sickrage

COPY config.ini /opt/sickrage/config.ini

EXPOSE 8081

ENTRYPOINT ["/usr/bin/python", "/opt/sickrage/SickBeard.py"]
