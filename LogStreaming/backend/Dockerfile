# Use the official Node.js image
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Copy package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy source files
COPY . .

# Expose port 4000 (or whatever port the server runs on)
EXPOSE 80

# Run the server
CMD ["node", "server.js"]
