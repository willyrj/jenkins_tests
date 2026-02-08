FROM nginx:latest

# Copy custom landing page
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80 (default nginx port)
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
