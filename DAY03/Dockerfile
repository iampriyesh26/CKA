FROM node:18-alpine3.21 AS installer

WORKDIR /app

COPY pack*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM ngin:latest AS deloyer

COPY --from=installer /app/build /usr/share/nginx/html