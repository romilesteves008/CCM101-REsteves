# Multi-Tier Architecture

## What is a Two-Tier Architecture?

A two-tier architecture splits an application into two separate layers that work together: a **web/application tier** that users interact with, and a **database tier** that stores the data. Each tier has its own job and communicates with the other over a network connection. In this mission, the two tiers are a Nextcloud container and a MariaDB container.

## The Web/Application Tier

The web/application tier is the part of the system users actually reach. It serves the user interface, handles HTTP requests from the browser, runs the application logic (logging in, uploading files, sharing folders), and talks to the database whenever it needs to read or save information. In this lab, the **Nextcloud container** is the application tier, and it is exposed to the outside world on port 8080.

## The Database Tier

The database tier is responsible for storing persistent data such as user accounts, passwords, file metadata, and settings. It does not serve web pages and is not meant to be reached directly by users. In this lab, the **MariaDB container** is the database tier, and only the Nextcloud container talks to it.

## Why Separate Them?

Putting the web server and the database in two separate containers makes each part easier to update, scale, and troubleshoot, because a problem or upgrade in one does not force a rebuild of the other. It is also more secure, since the database is not exposed to the public and only the application can reach it. Finally, it follows the container best practice of "one container, one job," which keeps each container small, simple, and reusable.
