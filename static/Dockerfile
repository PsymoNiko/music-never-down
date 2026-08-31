# frontend/Dockerfile
#FROM node:16

FROM ubuntu:14.04
ENV http_proxy="http://21.199.122.119:8080"
ENV https_proxy="https://21.199.122.119:8080"
# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the application
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]

