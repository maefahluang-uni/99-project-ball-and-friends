# Use node as base image
FROM node:15-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build Nuxt.js application
RUN npm run build

# Expose the port Nuxt.js is running on
EXPOSE 3000

# Command to run the application
CMD ["npm", "run", "start"]