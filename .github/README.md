
# NGINX Proxy Automation 🔥

<p align="center">
   <a target="_blank" href="https://docs.docker.com/"><img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white" /></a>
   <a target="_blank" href="https://docs.nginx.com/"><img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" /></a>
   <a target="_blank" href="https://developer.wordpress.org/"><img src="https://img.shields.io/badge/Wordpress-21759B?style=for-the-badge&logo=wordpress&logoColor=white" /></a>
</p>
<p align="center">
   <a target="_blank" href="https://letsencrypt.org/docs/"><img src="https://img.shields.io/badge/Secured_by-Let's_Encrypt-blue.svg?logo=let%E2%80%99s-encrypt" /></a>
</p>

<p align="center">
   <img src="https://github.com/evertramos/images/raw/master/webproxy.jpg" />
</p>

## How to start 🔰
[![shell script](https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)](https://github.com/evertramos)


1. Clone this repository using the option **_--recurse-submodules_** ⚠️

```bash
git clone --recurse-submodules https://github.com/qressy/nginx-proxy-automation.git proxy 
```

We use submodule for [basescript](https://github.com/evertramos/basescript)

2. 🚀 Run the script 'fresh_start.sh' from the _./proxy/bin_ folder
   
```bash
cd proxy/bin && ./fresh-start.sh --yes -e your_email@domain --skip-docker-image-check
```
Update the email above with your real e-mail address


2.1 ⭐ Start the nginx-proxy, docker-gen, letsencrypt(optional) docker containers (comment out letsencrypt container if not needed )

```bash
cd proxy && docker compose up -d
```
- This is a fork specific change ☝️


3. 🧪 Test the proxy

```bash
docker run -dit -e VIRTUAL_HOST=your.domain.com --network=proxy --name test-web httpd:alpine
```
or simply run:
```bash
./test.sh your.domain.com
```

Use your own domain name when testing this proxy and make sure your DNS is correctly configured.

## Trouble shoot

- while running docker compose up ( for proxy container )
```
Error response from daemon: driver failed programming external connectivity on endpoint proxy-web-auto (2def268a2143a64bfd06be3e1952afd54b6e644afc8dff9c666394275287f389): failed to bind port 0.0.0.0:80/tcp: Error starting userland proxy: error while calling PortManager.AddPort(): cannot expose privileged port 80, you can add 'net.ipv4.ip_unprivileged_port_start=80' to /etc/sysctl.conf (currently 1024), or set CAP_NET_BIND_SERVICE on rootlesskit binary, or choose a larger port number (>= 1024): listen tcp4 0.0.0.0:80: bind: permission denied
```

Solution:
```bash
# add 'net.ipv4.ip_unprivileged_port_start=80' to /etc/sysctl.conf
# to apply the change
sudo sysctl -p
# verify the change 
sysctl net.ipv4.ip_unprivileged_port_start
```

## Video Tutorial 🎥

I made a tutorial video to walk you through this project:

[![youtube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/channel/UCN5wb0eA3ZLlvJNYo23qBRQ)

### AWS EC2
<p align="center">
   <a target="_blank" href="https://www.youtube.com/watch?v=agg1VxAyoUQ"><img src="https://img.youtube.com/vi/agg1VxAyoUQ/0.jpg" /></a>
</p>

### Digital Ocean Droplet
<p align="center">
   <a target="_blank" href="https://www.youtube.com/watch?v=iXQPaY5xd3I"><img src="https://img.youtube.com/vi/iXQPaY5xd3I/0.jpg" /></a>
</p>

### OVH
<p align="center">
   <a target="_blank" href="https://www.youtube.com/watch?v=eiTivLeIkm0"><img src="https://img.youtube.com/vi/eiTivLeIkm0/0.jpg" /></a>
</p>

## Server Automation 🚀

Make user you try our [Server Automation](https://github.com/evertramos/server-automation)

[https://github.com/evertramos/server-automation](https://github.com/evertramos/server-automation)

## Further information 📓

For more installation details please [click here](/docs/).

## Supporting ♥️
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/evertramos)
[![image](https://img.shields.io/badge/picpay-21C25E?style=for-the-badge&logo=picpay&logoColor=white)](https://picpay.me/evert.ramos)

[List of all supporters](https://github.com/evertramos/evertramos/blob/main/pages/supporters.md).

## Code Contributors

[<img src="https://opencollective.com/nginx-proxy-automation/contributors.svg?width=890&button=false" />](https://opencollective.com/nginx-proxy-automation)
