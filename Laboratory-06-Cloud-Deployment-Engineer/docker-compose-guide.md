# Docker Compose Guide

This guide explains the `docker-compose.yml` file used to deploy the Nextcloud private cloud storage system.

## The Code

```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

## What does the `services:` block do?

The `services:` block lists every container that makes up the application. Each name directly under it (`database` and `app`) is one service, and each service has its own settings such as the image to use, environment variables, and ports. Docker Compose reads this block and creates one container per service. It also automatically places all the services on the same private network so they can talk to each other.

- `database` runs the **MariaDB 10.6** image and is created with a root password, a database name, a user, and that user's password.
- `app` runs the **Nextcloud** image, publishes container port 80 to port **8080** on the host (`8080:80`), and receives the database credentials it needs to connect.

## How did the Nextcloud app container find the database container?

Through the `MYSQL_HOST=database` environment variable. Docker Compose creates a private network for the stack, and on that network every service can be reached by its **service name**, which acts like a hostname. Because the database service is named `database`, the Nextcloud container simply connects to the host `database`, and Docker's built-in DNS resolves that name to the MariaDB container's IP address. No IP addresses had to be written by hand. The `MYSQL_DATABASE`, `MYSQL_USER`, and `MYSQL_PASSWORD` values in both services must match so Nextcloud can log in to the database.

## Difference between `docker run` and `docker-compose up -d`

| | `docker run` | `docker-compose up -d` |
|---|---|---|
| Containers started | One container per command | All services in the file at once |
| Configuration | Long options typed in the terminal (ports, env vars, etc.) | Saved in a reusable `docker-compose.yml` file |
| Networking | Containers must be linked or networked manually | A shared network is created automatically |
| Repeatability | Easy to make typing mistakes | Same result every time (Infrastructure as Code) |
| Cleanup | Stop and remove each container separately | `docker-compose down` removes everything |

In short, `docker run` is manual and one container at a time, while `docker-compose up -d` deploys the whole stack from code in the background (`-d` means detached mode).
