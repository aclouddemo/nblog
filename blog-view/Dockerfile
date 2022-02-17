FROM node:10.17.0-alpine3.9 as build-stage

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .
RUN npm run build

RUN ls -al

# Nginx
FROM nginx:alpine
LABEL maintainer="works | gexin"
COPY --from=build-stage /app/dist/ /usr/share/nginx/html/
COPY nginx/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
