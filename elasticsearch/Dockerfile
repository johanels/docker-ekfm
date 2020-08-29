FROM ubuntu

RUN apt update && \
    apt install -y curl gzip tar

RUN adduser --group elasticsearch && \
    adduser --system elasticsearch

WORKDIR /home/elasticsearch

USER elasticsearch:root

RUN curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.9.0-linux-x86_64.tar.gz && \
    tar zxvf elasticsearch-7.9.0-linux-x86_64.tar.gz --strip-components=1 && \
    rm -rf elasticsearch-7.9.0-linux-x86_64.tar.gz

ADD elasticsearch.yml config/elasticsearch.yml

RUN bin/elasticsearch-keystore create && \
    echo "12345678" | bin/elasticsearch-keystore add --stdin "bootstrap.password"

EXPOSE 9200 9300

ENTRYPOINT ["./bin/elasticsearch"]
