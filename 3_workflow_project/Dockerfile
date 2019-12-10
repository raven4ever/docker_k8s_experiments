FROM node:alpine AS builder

WORKDIR /app

COPY app/package.json ./
RUN npm install
COPY app/ ./

RUN npm run build


# runner container
FROM nginx:alpine
EXPOSE 80
COPY --from=builder /app/build /usr/share/nginx/html