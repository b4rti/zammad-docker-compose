FROM postgres:9.6-alpine
ARG BUILD_DATE

ENV BACKUP_SLEEP 86400
ENV HOLD_DAYS 14
ENV ZAMMAD_DIR /opt/zammad
ENV BACKUP_DIR /var/tmp/zammad

LABEL org.label-schema.build-date="$BUILD_DATE" \
      org.label-schema.name="Zammad" \
      org.label-schema.license="AGPL-3.0" \
      org.label-schema.description="Docker container for Zammad - Postgresql" \
      org.label-schema.url="https://zammad.org" \
      org.label-schema.vcs-url="https://github.com/b4rti/zammad" \
      org.label-schema.vcs-type="Git" \
      org.label-schema.vendor="Zammad" \
      org.label-schema.schema-version="1.2" \
      org.label-schema.docker.cmd="sysctl -w vm.max_map_count=262144;docker-compose up"

# copy backup script
COPY backup.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/backup.sh
