# Gebruik een officiële Nginx image
FROM nginx:alpine

# Kopieer bestanden naar de standaard webserver directory
COPY index.html /usr/share/nginx/html/index.html
COPY style.css /usr/share/nginx/html/style.css
COPY logo.png /usr/share/nginx/html/logo.png

# Expose poort 80 voor de webserver
EXPOSE 80
