# Comparing NGINX to Apache

## Similarities

- Free and open-source software
- Community of users reviewing the code
- Added functionality through dynamic modules
- Proxy servers
- Event-based processing for simultaneous connections

## Differences

| Apache                                               | NGINX                                          |
| ---------------------------------------------------- | ---------------------------------------------- |
| Config: XML Syntax                                   | Config: C-like Syntax                          |
| Distributed .htaccess file                           | Centralized location blocks                    |
| Dynamic content is natively processed with modules   | Dynamic content requires external processing   |
| Serving static content is less efficient             | More efficient at serving static content       |
| Caching and load-balancing capabilities with modules | Native caching and load-balancing capabilities |

## Why choose NGINX?

- Quickly becoming the leading web server
- Efficient and consistent under heavy load
- Easy to configure

<br>

# Set Up a Lab Server

## Public cloud service

- AWS
- Azure
- Google Cloud

<br>

# NGINX Command-Line Interface

Use the CLI to control NGINX
Elevate your session to use root permissions:

- sudo command
- sudo su - (become root user)

## Commands

Check status

> `systemctl status nginx`

Start

> `systemctl start nginx`

Reload

> `systemctl reload nginx`

NGINX

> `nginx -h`

<br>

# NGINX Files and Directories

Config

> `cd /etc/nginx`

<br>

Error Log

> `cd /var/log/nginx`

Content

> `cd /var/www`
