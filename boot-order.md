As the urbit's hosted on my Digital Ocean droplet use a static caddyfile for managing the reverse proxies to their web domains, if the VPS goes down or the urbits otherwise need to be shut down, they need to be re-booted in the proper order to ensure the port binding maps correctly to what is defined in the Caddyfile.
1. ~tocwex (bound to port 8080)
2. ~sarlev-sarsen (bound to port 8081)
3. ~lismyl-lismyl (bound to port 8082)
