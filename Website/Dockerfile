# Gebruik een officiële Nginx image
FROM nginx:alpine

# Kopieer bestanden naar de standaard webserver directory
COPY index.html /usr/share/nginx/html/index.html
COPY style.css /usr/share/nginx/html/style.css
COPY JL-logo.png /usr/share/nginx/html/JL-Logo.png

# Expose poort 80 voor de webserver
EXPOSE 80
