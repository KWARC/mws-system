# The MathWebSearch System

The MathWebSearch System, managed with Docker Compose. 
** Work in Progress **

- Docker Entry Point and Letsencrypt Setup
    - [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) - entry point taking care of https -> http
    - [jrcs/letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion) - Manages and renews letsencrypt certificates
- MWS System
    - [kwarc/mws](https://github.com/kwarc/mws) - the MWS daemon
    - [kwarc/mws-frontend](https://github.com/kwarc/mws-frontend) - a browser frontend to MWS

## Configuration

This repository supports both a local and production setup. 
All configuration is done via env files. 

These can be interactively generated using the configure script:

```bash
./configure
```

This script re-uses existing configuration if available. 
Furthermore, for a local setup, it is safe to accept all defaults. 

**WARNING:** Always shut down MWS before re-running the configuration script. 

## Starting and Stopping

**WARNING:** Do not attempt to run any of these commands without having gone through the configure script first. 

After having configured appropriatly, you can start the setup as follows:

```bash 
# to start all the containers
docker-compose up -d

# to stop the containers, but keep state
docker-compose down

# to stop all containers and remove all state
docker-compose down -v
```

** TODO ** Implement a way to update the index. 

## License

Licensed under GPL 3.0. 