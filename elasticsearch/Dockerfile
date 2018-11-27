FROM quay.io/pires/docker-elasticsearch:5.6.4

LABEL maintainer="tdviet12@gmail.com"

# Override config, otherwise plug-in install will fail
ADD config /elasticsearch/config

# Set environment
ENV DISCOVERY_SERVICE elasticsearch-discovery
ENV REMOTE_WHITELIST ''

# Kubernetes requires swap is turned off, so memory lock is redundant
ENV MEMORY_LOCK false
