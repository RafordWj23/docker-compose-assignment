# Stage 1: build the React app using Node.js 18
FROM node:18-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all the application files
COPY . .

# Build the production version of the app
RUN npm run build

# Stage 2: serve the built files with nginx
FROM nginx:alpine

# Copy the built files from the first stage into nginx
COPY --from=0 /app/dist /usr/share/nginx/html

# Document nginx's default port
EXPOSE 80

# Start nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]