# Load Balancing Web Servers

## Overview

This repository contains configuration and automation scripts to set up two Ubuntu web servers (`web-01` and `web-02`) behind a load balancer. Each server is configured to return a custom Nginx HTTP response header (`X-Served-By`) that helps us track which web server is responding to requests.

## Task

The goal of this task is to automate the configuration of two web servers with the following:

- Both servers (`web-01` and `web-02`) should include the custom HTTP header `X-Served-By` in the response.
- The value of the header should be the hostname of the server.
- This configuration should be automated with the script `0-custom_http_response_header`.

## Requirements

- Configure Nginx on both `web-01` and `web-02` to include the `X-Served-By` header with the correct hostname.
- Automate this configuration using the script `0-custom_http_response_header` so that a fresh Ubuntu server can be set up quickly.

## Steps to Complete

1. **Install Nginx:**
   - Ensure that Nginx is installed on both servers.

2. **Configure Nginx Custom Header:**
   - Edit the Nginx configuration to add the custom header `X-Served-By` with the hostname as its value.

3. **Automate Configuration with Bash Script:**
   - The script `0-custom_http_response_header` should automatically configure the server to include the custom header.

4. **Test the Configuration:**
   - After running the script, use the following `curl` commands to verify that the header is returned:
   
   ```bash
   curl -sI <server-ip> | grep X-Served-By
