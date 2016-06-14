FROM elasticsearch:5.0.0-alpha3
MAINTAINER Nicolas Ruflin <spam@ruflin.com>

# Dependencies
#ENV ES_IMAGE_PLUGIN_VER 1.7.1
ENV ES_PLUGIN_BIN /usr/share/elasticsearch/bin/elasticsearch-plugin

# Install Plugins
RUN ${ES_PLUGIN_BIN} install mapper-attachments
#RUN ${ES_PLUGIN_BIN} install delete-by-query
#RUN ${ES_PLUGIN_BIN} install image --url https://github.com/Jmoati/elasticsearch-image/releases/download/${ES_IMAGE_PLUGIN_VER}/elasticsearch-image-${ES_IMAGE_PLUGIN_VER}.zip

# Copy config files
COPY *.yml /usr/share/elasticsearch/config/
COPY scripts/* /usr/share/elasticsearch/config/scripts/


RUN mkdir -p /tmp/backups/backup1
RUN mkdir -p /tmp/backups/backup2

ENV ES_JAVA_OPTS="-Xms512m -Xmx512m"

# Expose standard ports
EXPOSE 9200 9300
