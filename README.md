# PersonalServURbit
This repository is the documentation of my personal server journey for the end goal of running a self-hosted and highly capable urbit (see urbit.org for more if you are curious). It will also contain documentation for the hosting of urbit ships on a digital ocean VPS

### Related Guides and skills
Tentative list of guides that I have heard exist and need to compile, review, understand, and adapt:
- Minio for S3 Buckets - https://www.notion.so/MinIO-S3-Urbit-a18a584293b3459e8785339e60145b11
- bitcoinD daemon - https://howchoo.com/bitcoin/run-bitcoin-full-node-raspberry-pi
- Bitcoind and elect.rs setup - https://subject.network/posts/pi-fullnode-urbit/
- bitcoin provider and wallet setup
- urbit.org documentation - https://urbit.org/docs/
- understanding SSH
- Smol Computer guide - https://bit.ly/smol-guide-rpi4
- accessing landscape with ssh - ~dasfeb/smol-bibliotheca/note/170141184504960759844397365188420960256
- detaching and reattaching terminal screens
- the tmux cheat sheet - https://tmuxcheatsheet.com/
- and any number of things I will continue to add to this list.

## Self-hosted ship
### Component Parts
1. Smol computer (rPi4) running Ubuntu
2. Urbit planet on said smol computer
3. BTC node
4. electrum instance
5. BTC provider agent
6. BTC wallet
7. Lightning Node

### Goals
- Be able to run my own instance of the Bitcoin blockchain
- connect mobile lightning wallet to personally owned Lightning node
- Use Minio to run S3 buckets locally for use with Urbit
- encrypt at rest, if possible.
- Be able to SSH into rPi from remote locations
- be able to access Urbit using Tailscale
- Digital Sovereignty

## Digtial Ocean Droplet Ships
### Component Parts
1. Digital Ocean Droplet
2. Urbit stars/planets/moons
3. S3 Buckets using DO Spaces
4. Caddy webserver
5. ssh
6. tmux

### Goals
- maintain high uptime and remote accessibility, particularly for stars
- easy serving of terran webpages using %studio
