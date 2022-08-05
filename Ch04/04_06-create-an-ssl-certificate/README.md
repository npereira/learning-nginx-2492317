# 04_06 Create an SSL certificate

An SSL certificate is a digital certificate that authenticates a website's identity and helps encrypt the connection between a browser and a web server.

## Create a Self-Signed SSL Certificate
Check for the `openssl` command on your system: `which openssl`.

Install `openssl` if needed: `sudo apt install -y openssl`.

Use the following command to:
- Create a private key
- Sign the certificate with the key
- Store the certificate and key in locations accessible to NGINX

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx.key -out /etc/ssl/certs/nginx.crt -batch
```