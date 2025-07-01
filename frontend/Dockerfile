# --- Stage 1: Build ---
FROM node:18 AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# --- Stage 2: Serve ---
FROM node:18

WORKDIR /app
COPY --from=builder /app /app

RUN npm install -g serve

EXPOSE 4000
CMD ["serve", "-s", "dist", "-l", "4000"]

