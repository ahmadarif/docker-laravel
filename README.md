# Description

    Docker image for Laravel/Lumen Apps

## Sample Usage with caching

    ```Dockerfile
    # 1: Install dependencies
    FROM composer:2.0.6 as build-stage

    WORKDIR /var/www/html
    COPY . .
    RUN composer install

    # 2: Main app
    FROM ahmadarif/docker-laravel:latest

    COPY --from=build-stage /var/www/html /var/www/html
    EXPOSE 80
    ENTRYPOINT ["/usr/bin/supervisord"]
    ```
