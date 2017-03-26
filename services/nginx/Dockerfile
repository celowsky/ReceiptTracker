FROM nginx:mainline

# Removes default Nginx configuration
RUN ["rm", "/etc/nginx/conf.d/default.conf"]

# Adds custom Nginx configuration
COPY ./nginx.conf /etc/nginx/
COPY ./ReceiptTracker.conf /etc/nginx/sites-available/

## Enables custom config for Nginx
RUN ["mkdir", "/etc/nginx/sites-enabled/"]
RUN ["ln", "-s", "/etc/nginx/sites-available/ReceiptTracker.conf", "/etc/nginx/sites-enabled/ReceiptTracker.conf"]
