FROM python:3-slim

# Set the working directory
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install the required packages
RUN pip install -r requirements.txt

# Set environment variables
ENV PORT=3000
ENV INSTANCE_NAME=""
ENV INSTANCE_HASH=""

HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
  CMD curl http://localhost:${PORT}/healthz || exit 1

EXPOSE ${PORT}

# Make run.sh executable
RUN chmod +x run.sh

# Define the entry point
ENTRYPOINT /app/run.sh
