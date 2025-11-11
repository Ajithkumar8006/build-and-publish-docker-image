# Start from the official nginx image
FROM nginx:alpine

# Copy your index.html
COPY ./index.html /usr/share/nginx/html/index.html

# Replace the default nginx.conf with one that uses $PORT dynamically
RUN rm /etc/nginx/conf.d/default.conf

# Add a dynamic configuration that reads PORT from env
# Cloud Run will pass $PORT (usually 8080)
RUN echo 'server { \
    listen ${PORT}; \
    location / { \
        root /usr/share/nginx/html; \
        index index.html; \
    } \
}' > /etc/nginx/conf.d/default.conf

# Expose port 8080 for local testing
EXPOSE 8080

# Start nginx normally
CMD ["nginx", "-g", "daemon off;"]
