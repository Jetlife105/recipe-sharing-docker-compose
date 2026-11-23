
# Use Node.js 18 Alpine
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy application files
COPY . .

# Create directory for SQLite database
RUN mkdir -p /app/data

# Expose backend port
EXPOSE 5000

# Start backend application
CMD ["npm", "start"]
