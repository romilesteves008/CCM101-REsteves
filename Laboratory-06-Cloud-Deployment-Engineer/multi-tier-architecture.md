# Two-Tier Architecture

Two-Tier Architecture is a system design that separates an application into two main parts: the Web/Application Tier and the Database Tier. These two tiers communicate with each other to process requests and manage data.

## 1. The Web/Application Tier

The Web/Application Tier handles user interactions and displays the website or application interface. It receives HTTP requests from users, processes them, and communicates with the database when information is needed.

## 2. The Database Tier

The Database Tier stores and manages persistent data, such as user accounts, passwords, product information, and transaction records. It responds to database queries from the Web/Application Tier.

## 3. Why Separate Them?

Separating the web server and database into two containers improves security because the database can be isolated from direct public access. It also makes maintenance and scaling easier because each container can be managed or updated independently.

