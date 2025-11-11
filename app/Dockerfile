    FROM nginx:stable-alpine
    COPY nginx.conf /etc/nginx/nginx.conf
    COPY html /usr/share/nginx/html # If serving static content
    EXPOSE 8080
    CMD ["nginx", "-g", "daemon off;"]
