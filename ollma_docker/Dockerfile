# Use the official Ollama image as the base image
FROM ollama/ollama:latest AS builder

FROM alpine:latest

# Set the working directory
WORKDIR /app

COPY --from=builder /app/out/server .

# Expose the port Ollama uses
EXPOSE 11434

RUN adduser \
  --disabled-password \
  --gecos "" \
  --home "/nonexistent" \
  --shell "/sbin/nologin" \
  --no-create-home \
  --uid 10014 \
  "choreo"

  USER 10014

# Define the command to run when the container starts
CMD ["ollama", "serve"]
