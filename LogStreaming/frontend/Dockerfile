# Step 1: Build React app
FROM node:18 as build

WORKDIR /app

# Copy package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy source files and build the production-ready React app
COPY . .
RUN npm run build

# Step 2: Serve React app with Nginx
FROM nginx:1.23.3-alpine

# Copy build output from the previous step to Nginx's default static file directory
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Run Nginx
CMD ["nginx", "-g", "daemon off;"]
