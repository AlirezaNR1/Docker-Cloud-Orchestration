# Set the base image
FROM node:slim

# Set the working directory
WORKDIR /app

# Copy all files from the current directory to the container
COPY . .

# Install dependencies
# RUN npm install

# Expose the port the app will run on
EXPOSE 8003

# Set the network alias
# RUN echo "jsapp" >> /etc/hosts

# Start the app
CMD ["node", "PingPong.js"]
