# Use the official lightweight Nginx image
FROM nginx:alpine

# Copy a custom Nginx config file if you have one (optional)
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 8080 to match Cloud Run's expected PORT environment variable
EXPOSE 8080

# Run Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
