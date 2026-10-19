   # Use Node.js 18 on lightweight Alpine Linux
   FROM node:18-alpine

   # Set working directory inside the container
   WORKDIR /app

   # Copy package files first (for better caching)
   COPY package*.json ./

   # Install dependencies
   RUN npm install

   # Copy the rest of the application files
   COPY . .

   # Create a directory for the SQLite database file
   RUN mkdir -p /app/data

   # Document the port the backend runs on
   EXPOSE 5000

   # Start the application
   CMD ["npm", "start"]