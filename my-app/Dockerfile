FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies and print debug logs if failed
RUN npm install || (echo "=== NPM INSTALL FAILED ===" && \
    echo "Dumping npm logs:" && \
    find /root/.npm/_logs -type f && \
    cat /root/.npm/_logs/* || true && false)

# Copy source code
COPY . .

EXPOSE 3000

CMD ["npm", "start"]
