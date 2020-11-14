```
FROM ahmadarif/docker-laravel

# Copy Resources
COPY . /var/www/html

# Install dependencies
RUN composer install

# Expose port 80
EXPOSE 80

# Set supervisor to manage container processes
ENTRYPOINT ["/usr/bin/supervisord"]
```