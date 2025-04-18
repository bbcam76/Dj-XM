# .devcontainer/Dockerfile
FROM mcr.microsoft.com/vscode/devcontainers/python:3.11

# Install PostgreSQL client for Django DB connectivity
RUN apt-get update \
 && apt-get install -y postgresql-client \
 && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /workspace

# Copy and install Python dependencies early to leverage Docker cache
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Default to non-root user provided by the base image
