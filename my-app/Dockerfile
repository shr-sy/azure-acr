# Stage 1: Build the app
FROM node:18-alpine AS builder

WORKDIR /app

# Install dependencies early for caching
COPY package*.json ./
RUN npm install

# Copy source code
COPY . .

# Optional: run build script if using React, TypeScript, etc.
# RUN npm run build

# Stage 2: Production image
FROM node:18-alpine

WORKDIR /app

# Copy only necessary files from builder
COPY --from=builder /app .

# Expose the port your app runs on
EXPOSE 3000

# Default command to run the app
CMD ["node", "server.js"]
