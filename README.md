# HTTPS SSL Configuration with HAProxy

This repository contains HAProxy load balancer configurations designed to implement secure HTTPS traffic, SSL termination, and automatic HTTP-to-HTTPS redirection for web servers.

## Project Structure

* **`1-haproxy_ssl_termination`**: 
  HAProxy configuration file that configures SSL termination. It binds to port 80 (HTTP) and port 443 (HTTPS) using a combined SSL certificate (`.pem`), forwarding traffic back to backend servers.

* **`2-redirect_http_to_https`**: 
  HAProxy configuration file that implements a secure traffic flow by automatically and permanently redirecting (HTTP 301) all insecure incoming HTTP traffic on port 80 to secure HTTPS on port 443.

## How to Test and Run

1. **Verify HAProxy configuration syntax**:
   ```bash
   sudo haproxy -f /etc/haproxy/haproxy.cfg -c
Restart the service to apply changes:

Bash
sudo service haproxy restart
Verify HTTP to HTTPS Redirection:

Bash
curl -I http://localhost
Expected output: HTTP/1.1 301 Moved Permanently pointing to https://localhost/.

Author
Nshimiyimana Abdurahim


### What to do next:
You can quickly copy this file over into your directory or run this in your terminal to save it directly:

```bash
cat << 'EOF' > README.md
# HTTPS SSL Configuration with HAProxy

This repository contains HAProxy load balancer configurations designed to implement secure HTTPS traffic, SSL termination, and automatic HTTP-to-HTTPS redirection for web servers.

## Project Structure

* **`1-haproxy_ssl_termination`**: 
  HAProxy configuration file that configures SSL termination. It binds to port 80 (HTTP) and port 443 (HTTPS) using a combined SSL certificate (`.pem`), forwarding traffic back to backend servers.

* **`2-redirect_http_to_https`**: 
  HAProxy configuration file that implements a secure traffic flow by automatically and permanently redirecting (HTTP 301) all insecure incoming HTTP traffic on port 80 to secure HTTPS on port 443.

## How to Test and Run

1. **Verify HAProxy configuration syntax**:
   ```bash
   sudo haproxy -f /etc/haproxy/haproxy.cfg -c
