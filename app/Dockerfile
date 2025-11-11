FROM nginx:alpine

# Copy static file (optional)
COPY ./index.html /usr/share/nginx/html/index.html

# Replace listen port dynamically with $PORT (Cloud Run sets this env var)
RUN sed -i 's/listen\s\+80;/listen ${PORT};/' /etc/nginx/conf.d/default.conf

EXPOSE 8080

# Start Nginx (PORT env var will be substituted at runtime)
CMD ["/bin/sh", "-c", "sed -i 's/${PORT}/'\"$PORT\"'/g' /etc/nginx/conf.d/default.conf && nginx -g 'daemon off;'"]
