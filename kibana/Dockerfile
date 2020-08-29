FROM ubuntu

# Drop everything here
WORKDIR /opt

# Add dependencies
RUN apt update && \
    apt install -y curl tar gzip

# Add Kibana
RUN curl -L -O https://artifacts.elastic.co/downloads/kibana/kibana-7.9.0-linux-x86_64.tar.gz && \
    tar zxvf kibana-7.9.0-linux-x86_64.tar.gz --strip-components=1 && \
    rm -rf kibana-7.9.0-linux-x86_64.tar.gz

# Default Kibana setup
ADD kibana.yml /opt/config/kibana.yml 

# Default Kibana WEB interface port    
EXPOSE 5601

# Run Kibana at start
ENTRYPOINT ["./bin/kibana", "--allow-root"]
