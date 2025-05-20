# Use a base image for the application service
FROM ollama/ollama:latest

# Expose port 11434 (assuming the application listens on this port)
EXPOSE 11434

# Define a volume for storing Ollama data
VOLUME /root/.ollama

# Install curl (assuming it's not already installed in the base image)
RUN apt-get update && apt-get install -y curl
 
# Define volumes
VOLUME ollama_data

# Copy the entrypoint script into the image
COPY entrypoint.sh /usr/local/bin/entrypoint.sh

# Make the script executable
RUN chmod +x /usr/local/bin/entrypoint.sh

# Set the entrypoint to the script
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
