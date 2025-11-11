FROM nginx:alpine

# Copy default html
COPY ./index.html /usr/share/nginx/html/index.html

# Replace the listen port in nginx.conf with the PORT env variable
RUN sed -i 's/listen       80;/listen       ${PORT};/' /etc/nginx/conf.d/default.conf

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
