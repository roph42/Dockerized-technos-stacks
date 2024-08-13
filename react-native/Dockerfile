FROM node:latest AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN expo build

FROM node:alpine
WORKDIR /app
COPY --from=builder /app/build /app
EXPOSE 8081
CMD ["node", "index.js"]