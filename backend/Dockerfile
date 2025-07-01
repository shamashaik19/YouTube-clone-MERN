FROM node:18

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy remaining files
COPY . .

# Use environment variables at runtime (don’t hardcode)
ENV DB_user=${DB_user}
ENV DB_password=${DB_password}
ENV DB_name=${DB_name}
ENV SECRET_KEY=${SECRET_KEY}
ENV EMAIL=${EMAIL}
ENV PASSWORD=${PASSWORD}

EXPOSE 5000
CMD ["node", "server.js"]

