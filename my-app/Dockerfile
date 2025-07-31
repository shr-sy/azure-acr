FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy only package files first
COPY package*.json ./

# Install dependencies and capture logs
RUN npm install || (cat /root/.npm/_logs/*-debug-*.log && false)

# Copy app source
COPY . .

# Expose port (optional, change if needed)
EXPOSE 3000

# Default command (adjust if needed)
CMD ["npm", "start"]
