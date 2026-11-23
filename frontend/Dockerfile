
# Stage 1: Build React application
FROM node:18-alpine

WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy frontend source
COPY . .

# Set API URL for Vite production build
ARG VITE_API_URL=http://localhost:5000
ENV VITE_API_URL=$VITE_API_URL

# Build production application
RUN npm run build

# Stage 2: Serve with nginx
FROM nginx:alpine

# Copy built frontend files
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose nginx port
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
