FROM prom/prometheus:latest

# Create directories for Prometheus and set permissions in one layer
USER root
RUN mkdir -p /etc/prometheus /prometheus && \
    chown -R nobody:nobody /etc/prometheus /prometheus

# Copy configuration file with correct ownership
COPY --chown=nobody:nobody prometheus.yml /etc/prometheus/prometheus.yml

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