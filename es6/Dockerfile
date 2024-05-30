FROM debian:bookworm

WORKDIR /usr/share
RUN adduser --group app && adduser --system app --ingroup app

ADD --chown=app:app https://corretto.aws/downloads/latest/amazon-corretto-8-aarch64-linux-jdk.tar.gz /usr/share/

RUN tar -xzf /usr/share/amazon-corretto-8-aarch64-linux-jdk.tar.gz \ 
    && rm /usr/share/amazon-corretto-8-aarch64-linux-jdk.tar.gz \
    && mv /usr/share/amazon-corretto* /usr/share/jdk \
    && chown app:app -R /usr/share/jdk

ENV LANG C.UTF-8
ENV JAVA_HOME=/usr/share/jdk

ADD --chown=app:app https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.8.23.tar.gz /usr/share/
RUN tar -xzf /usr/share/elasticsearch-6.8.23.tar.gz \ 
    && rm /usr/share/elasticsearch-6.8.23.tar.gz \
    && mv /usr/share/elasticsearch-6.8.23* /usr/share/elasticsearch \
    && chown app:app -R /usr/share/elasticsearch

EXPOSE 9200 9300

USER app
CMD cd /usr/share/elasticsearch/bin/ && ./elasticsearch