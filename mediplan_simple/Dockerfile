FROM nginx:stable-alpine
ENV DEBIAN_FRONTEND=noninteractive
COPY ./index.html /usr/share/nginx/html/index.html
COPY ./js.js /usr/share/nginx/html/js.js
COPY ./style.css /usr/share/nginx/html/style.css
EXPOSE 80
