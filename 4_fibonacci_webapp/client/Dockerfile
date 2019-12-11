FROM node:alpine AS builder

WORKDIR /app

COPY package.json ./
RUN npm install
COPY . .

RUN npm run build


# runner container
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
COPY nginx/default.conf /etc/nginx/conf.d/default.conf
EXPOSE 3000