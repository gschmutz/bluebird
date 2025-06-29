# Use an official Node.js runtime as a base image
FROM node:23-slim

ARG VERSION=latest

# Install the Bluebird CLI globally (if needed)
#RUN npm install -g @sdairs/bluebird@${VERSION}

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first (for better layer caching)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your application code
COPY . .

# If your app has a build step (e.g., TypeScript or bundling), include it
#RUN npm run build

# Copy the entrypoint shell script
COPY ./entrypoint.sh /usr/local/bin/entrypoint.sh

# Make the shell script executable
RUN chmod +x /usr/local/bin/entrypoint.sh

# Set the entrypoint to use the entrypoint script
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]

