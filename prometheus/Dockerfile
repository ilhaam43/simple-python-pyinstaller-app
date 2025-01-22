FROM prom/prometheus:latest

# Create directories for Prometheus
RUN mkdir -p /etc/prometheus && \
    mkdir -p /prometheus

# Copy configuration file
COPY prometheus.yml /etc/prometheus/prometheus.yml

# Set permissions
RUN chown -R nobody:nobody /etc/prometheus /prometheus

# Expose the port
EXPOSE 9091

# Set user
USER nobody

# Set entrypoint
ENTRYPOINT [ "/bin/prometheus" ]

# Set command
CMD [ "--config.file=/etc/prometheus/prometheus.yml", \
      "--storage.tsdb.path=/prometheus", \
      "--web.console.libraries=/usr/share/prometheus/console_libraries", \
      "--web.console.templates=/usr/share/prometheus/consoles", \
      "--web.listen-address=:9091" ]