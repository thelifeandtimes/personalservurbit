As the urbit's hosted on my Digital Ocean droplet use a static caddyfile for managing the reverse proxies to their web domains, if the VPS goes down or the urbits otherwise need to be shut down, they need to be re-booted in the proper order to ensure the port binding maps correctly to what is defined in the Caddyfile.
1. ~sarlev-sarsen (bound to port 8080)
2. ~tocwex (bound to port 8081)
3. ~sartyr (bound to port 8082)
4. ~lismyl-lismyl (bound to port 8083)

As my caddyfile lives in the home directory, to start caddy, use `caddy start --config ~/Caddyfile` and caddy will start and run in the background.
