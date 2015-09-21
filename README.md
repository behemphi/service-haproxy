# Purpose

This repo contains the processes necessary to build a dynamic haproxy container
that acts as a load balancer to http backends.

# Overview

Conceptually, this container is meant to be balance *n* number of backend
http services.  These will typically be nginx  
e.g. [nginx-backend-eg](http://github.com/stackhub/nginx-backend-eg) or 
[apache-backend-eg](http://github.com/stackhub/apache-backend-eg)

However a golang binary or Tomcat service that answers httpd requests would 
also work as well.

The container checks every 5 seconds for new services at its serivce key.  
When it sees a change, it rewrites the haproxy.cfg file and reloads
the haproxy service. 

# Usage

For example usage, please see the 
[stack-haproxy repo](http://github.com/stackhub/stack-haproxy).

# License

MIT