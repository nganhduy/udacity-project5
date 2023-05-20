FROM node:16-alpine AS build
WORKDIR /app

COPY . .
RUN npm install
RUN npm run build
# Serve Application using Nginx Server
FROM nginx
COPY /nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/dist/angular-app/ /usr/share/nginx/html
EXPOSE 80