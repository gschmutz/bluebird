# Use an official Node.js runtime as a base image
FROM node:23-slim

ARG VERSION=latest

RUN npm install -g @sdairs/bluebird@${VERSION}

# Copy the entrypoint shell script
COPY ./entrypoint.sh /usr/local/bin/entrypoint.sh

# Make the shell script executable
RUN chmod +x /usr/local/bin/entrypoint.sh

# Set the entrypoint to use the entrypoint script
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]

