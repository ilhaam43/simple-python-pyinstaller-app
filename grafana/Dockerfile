FROM grafana/grafana:latest

USER root

# Create necessary directories
RUN mkdir -p /var/lib/grafana && \
    mkdir -p /var/log/grafana && \
    mkdir -p /var/lib/grafana/plugins

# Set permissions using root user
RUN chown -R grafana:root /var/lib/grafana && \
    chown -R grafana:root /var/log/grafana && \
    chmod -R 777 /var/lib/grafana && \
    chmod -R 777 /var/log/grafana

# Expose the port
EXPOSE 3031

# Set environment variables
ENV GF_SECURITY_ADMIN_PASSWORD=admin \
    GF_SECURITY_ADMIN_USER=admin \
    GF_SERVER_HTTP_PORT=3031

# Switch back to grafana user
USER grafana