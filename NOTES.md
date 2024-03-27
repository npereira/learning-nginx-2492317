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

<br>

# Configure Locations

## Location Directive

Extends the configuration based on the uniform resource indicator (URI)

> `location [modifier] location_definition { ... }`

## Location Modifiers

| Modifier | Application to Location Definitions                                      |
| -------- | ------------------------------------------------------------------------ |
| None     | The location definition is interpreted as a prefix for the URI           |
| =        | The URI must be an exact match to the location definition                |
| ~        | The location definition is used as a case-sensitive regular expression   |
| ~\*      | The location definition is used as a case-insensitive regular expression |
| ^~       | If the longest prefix matches, then no regular expressions are checked   |

## Location Definitions

| Prefix string            | Regular expression             |
| ------------------------ | ------------------------------ |
| "=" modifier is optional | Modifiers are required         |
| Checked first            | Checked in order of appearance |

## Location Processing

1. Exact match location `= /index.html`
2. Prefix location `/index.html`
3. Regular expression location `~* /index.html`

# NGINX Logs

Access logs

- Time of the request
- Result of the request
- Client IP address
- Client browser

Error logs

- Configuration errors
- Service stops and starts
- Service errors

<br>

`/etc/nginx/nginx.conf`

`

    http {
    ...
    access_log /var/log/nginx/access.log;
    error_log /var/log/nginx/error.log;
    ...
    }

`

# Troubleshooting problems with NGINX

- `nginx -t`
- Check for configuration file typos
- `systemctl status nginx`
- `systemctl reload nginx`
- Check the ports
  - sudo lsof -i :80 -i :443 | grep nginx
  - sudo apt install net-tools
  - sudo netstat -plan | grep nginx
- `tail -f /var/logs/nginx/*.log`
