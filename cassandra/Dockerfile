FROM datastax/dse-server:6.8.32

RUN sed -i 's/cdc_enabled: false/cdc_enabled: true/g' /opt/dse/resources/cassandra/conf/cassandra.yaml
RUN sed -i "s/commitlog_sync_period_in_ms: 10000/commitlog_sync_period_in_ms: 2000/g" /opt/dse/resources/cassandra/conf/cassandra.yaml
RUN echo "cdc_total_space_in_mb: 5000" >> /opt/dse/resources/cassandra/conf/cassandra.yaml
RUN echo "cdc_raw_directory: /var/lib/cassandra/cdc_raw" >> /opt/dse/resources/cassandra/conf/cassandra.yaml

COPY ./agent-dse4-2.2.3-all.jar /

# Add cassandra tools in the PATH
ENV PATH="${PATH}:/opt/dse/resources/cassandra/tools/bin/"