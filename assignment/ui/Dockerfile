FROM nginx:1.25-alpine

# Remove the default nginx config and replace with ours
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy static UI files
COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80

# This command checks if the config is valid before starting
# It helps us catch errors in the pipeline
CMD ["nginx", "-t"] && nginx -g "daemon off;"