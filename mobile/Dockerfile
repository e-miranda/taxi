# Dockerfile for React Native App

FROM node:18

# Set the working directory in the container
WORKDIR /app

# Install dependencies
COPY package.json .
COPY yarn.lock .
RUN yarn install

# Copy the rest of your application code
COPY . .

# Start the application
CMD ["yarn", "start"]