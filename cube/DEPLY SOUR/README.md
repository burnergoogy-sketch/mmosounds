# Sour (Cube 2 in the browser, with multiplayer) - deploy kit

Sour is a server program, not a folder of web files. It must run on a Linux server
(VPS, cloud VM, Fly.io, Railway...). GoDaddy shared/Airo web hosting cannot run it.

## Needs
- Linux x86-64 server, ~1 GB disk, 1 GB+ RAM
- Docker + Docker Compose
- A domain/subdomain pointing at the server (HTTPS is required for browsers)
- Ports 80 + 443 open (and UDP 28785 if you want desktop-client players)

## Steps
1. Copy this folder to the server.
2. Edit `Caddyfile`: replace play.example.com with your domain.
3. `docker compose up -d --build`
4. Open https://your-domain/ - players share the same lobby/servers.

## Notes
- Release v0.2.5 includes the base game + a few maps (complex, dust2, turbine...).
  More maps means building sour's asset bundles yourself (see the repo's assets/ folder).
- Link from GoDaddy: add a button/link (or an iframe) on your Airo site pointing to
  https://your-domain/
- Local test without Docker: extract the release tarball and run ./sour, then open http://localhost:1337
