FROM bitnami/minideb-extras:jessie-r23
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages libbsd0 libc6 libedit2 liblzma5 libssl1.0.0 libtinfo5 libxml2 libxslt1.1 zlib1g
RUN bitnami-pkg unpack postgresql-10.2.0-0 --checksum f7fcd851bc9480e01e9e09115bf9f49ece51c0b0385d9f631db0af9f124f638e

COPY rootfs /

ENV BITNAMI_APP_NAME="postgresql" \
    BITNAMI_IMAGE_VERSION="10.2.0-r0" \
    PATH="/opt/bitnami/postgresql/bin:$PATH" \
    POSTGRESQL_DATABASE="" \
    POSTGRESQL_MASTER_HOST="" \
    POSTGRESQL_MASTER_PORT_NUMBER="5432" \
    POSTGRESQL_PASSWORD="" \
    POSTGRESQL_PORT_NUMBER="5432" \
    POSTGRESQL_REPLICATION_MODE="master" \
    POSTGRESQL_REPLICATION_PASSWORD="" \
    POSTGRESQL_REPLICATION_USER="" \
    POSTGRESQL_USERNAME="postgres"

EXPOSE 5432

ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["nami","start","--foreground","postgresql"]