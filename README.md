WordPress with MySQL using Docker Compose

This repository contains a docker-compose.yml file to set up a WordPress website with a MySQL database using Docker.
Prerequisites

Ensure you have the following installed on your system:

    Docker
    Docker Compose

Services

This setup includes two main services:

    WordPress
        Uses the latest WordPress image.
        Accessible on port 80.
        Data is persisted using a Docker volume (wordpress_files).

    MySQL
        Uses the latest MySQL image.
        Accessible on port 3306.
        Stores data in a Docker volume (db_data).

Configuration

    WordPress connects to the database using the following environment variables:
        WORDPRESS_DB_HOST: db:3306
        WORDPRESS_DB_USER: wordpress
        WORDPRESS_DB_PASSWORD: wordpresspassword
        WORDPRESS_DB_NAME: wordpress

    MySQL is configured with:
        MYSQL_ROOT_PASSWORD: myrootpassword
        MYSQL_DATABASE: wordpress
        MYSQL_USER: wordpress
        MYSQL_PASSWORD: wordpresspassword

Usage

Start the containers:
    ```sh
    docker-compose up -d
    ```
Access WordPress: Open your browser and visit: http://localhost

Stop the containers:
    ```sh
    docker-compose down
    ```

Volumes

This setup uses Docker volumes to persist data:

    wordpress_files: Stores WordPress files.
    db_data: Stores MySQL database files.

Customization

You can modify the docker-compose.yml file to:

    Change port mappings.
    Use a different database name, user, or password.
    Add additional services (like phpMyAdmin).

Troubleshooting

To view logs, use:
    ```sh
    docker-compose logs -f
    ```
To access the WordPress container shell:
    ```sh
    docker exec -it <container_name> bash
    ```
    
    
