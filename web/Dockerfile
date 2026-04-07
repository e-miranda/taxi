# Dockerfile for React Admin Dashboard with Node.js 18 and Vite

# Use the official Node.js 18 as the base image
FROM node:18

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install project dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Build the application for production
RUN npm run build

# Expose port 3000
EXPOSE 3000

# Command to run the application
CMD [ "npm", "run", "preview" ]
