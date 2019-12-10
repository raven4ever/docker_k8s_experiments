FROM node:alpine AS builder

WORKDIR /app

COPY ./app/package.json ./
RUN npm install
COPY ./app/ ./

RUN npm run build


# runner container
FROM nginx:alpine

COPY --from=builder /app/build /usr/share/nginx/html