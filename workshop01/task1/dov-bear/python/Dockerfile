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

# Make run.sh executable
RUN chmod +x run.sh

# Define the entry point
ENTRYPOINT /app/run.sh
