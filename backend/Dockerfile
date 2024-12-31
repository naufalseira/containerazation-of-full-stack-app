# Build stage
FROM node:22-alpine AS build

WORKDIR /app

# Install OpenSSL
RUN apk add --no-cache openssl

# Copy package files
COPY package*.json ./
COPY prisma ./prisma/

# Install dependencies
RUN npm install

# Copy source code
COPY . .

# Prisma generate client
RUN npx prisma generate

# Development stage
FROM node:22-alpine AS development

WORKDIR /app

# Install OpenSSL
RUN apk add --no-cache openssl

# Copy from build stage
COPY --from=build /app /app

# Expose port
EXPOSE 8000

# Start development server
CMD ["npm", "run", "start:dev"]