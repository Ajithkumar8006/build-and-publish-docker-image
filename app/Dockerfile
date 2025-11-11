FROM nginx:alpine

COPY ./index.html /usr/share/nginx/html/index.html

# Replace the default nginx config so it uses the Cloud Run PORT variable
RUN rm /etc/nginx/conf.d/default.conf
RUN echo 'server { \
    listen ${PORT}; \
    location / { \
        root /usr/share/nginx/html; \
        index index.html; \
    } \
}' > /etc/nginx/conf.d/default.conf

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
