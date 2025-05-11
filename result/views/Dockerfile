FROM python:3.11-slim

# Add curl for healthcheck and tini for process management
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl tini && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY main.py .

# Set port and expose it
ENV PORT=80
EXPOSE 80

# Use tini as init system
ENTRYPOINT ["/usr/bin/tini", "--"]
CMD ["python", "main.py"]

