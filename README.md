# Docker_IA_2

# NEXT.js Dockerfile
# As this is the next.js no need to create two seperate dockerfile for frontend and backend

# Use the official Node.js 14 image as the base image
FROM node:14
# Set the working directory inside the container
WORKDIR /usr/src/app
# Copy package.json and package-lock.json files to the working directory
COPY package*.json ./
# Install dependencies defined in package.json
RUN npm install
# Copy the rest of the application code to the working directory
COPY . .
# Expose port 3000 to allow outside access to the application
EXPOSE 3000
# Define the command to start the application
CMD ["npm", "run", "dev"]




# Mongo Docker file
# Use the official MongoDB image as the base image
FROM mongo
# Define the command to start the MongoDB server
CMD ["mongod"]

