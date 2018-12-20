FROM tomcat:7-jre8

LABEL maintainer="MultimediaUGent <multimedia@ugent.be>" \
       org.label-schema.schema-version="1.0" \
       org.label-schema.version="6.0" \
       org.label-schema.name="opencast-solr-search" \
       org.label-schema.description="Docker image for the Opencast solr search service" \
       org.label-schema.usage="https://github.com/ICTO/docker-solr-opencast/blob/master/README.md" \
       org.label-schema.url="http://www.opencast.org/" \
       org.label-schema.vcs-url="https://github.com/ICTO/docker-solr-opencast" \
       org.label-schema.vendor="Ghent University" \
       org.label-schema.docker.debug="docker exec -it $CONTAINER sh"
       
ARG solr="http://archive.apache.org/dist/lucene/solr/1.4.1/apache-solr-1.4.1.zip"

RUN curl -O "${solr}" \
&& unzip apache-solr-1.4.1.zip \
&& unzip apache-solr-1.4.1/example/webapps/solr.war -d /usr/local/tomcat/webapps/solr/ \
&& rm apache-solr-1.4.1.zip \
&& rm -r apache-solr-1.4.1 \
&& mkdir -p /var/lib/solr/data

COPY assets/solr /usr/local/tomcat/solr
COPY assets/opencast-solr-5.1.jar /usr/local/tomcat/webapps/solr/WEB-INF/lib
