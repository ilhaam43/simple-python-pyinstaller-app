FROM grafana/grafana:latest

USER root

# Create necessary directories
RUN mkdir -p /var/lib/grafana && \
    mkdir -p /var/log/grafana && \
    mkdir -p /var/lib/grafana/plugins

# Set permissions
RUN chown -R grafana:grafana /var/lib/grafana && \
    chown -R grafana:grafana /var/log/grafana

# Switch back to grafana user
USER grafana

# Expose the port
EXPOSE 3031

# Set environment variables
ENV GF_SECURITY_ADMIN_PASSWORD=admin \
    GF_SECURITY_ADMIN_USER=admin \
    GF_SERVER_HTTP_PORT=3031