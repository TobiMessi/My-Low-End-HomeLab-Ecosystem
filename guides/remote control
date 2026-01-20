This single guide contains every command and configuration used to build my setup. It is optimized for budget hardware (like an i5-3470 with 8GB RAM) and 100% mobile management.

---

Phase 1: System Preparation & Docker Engine
Run this massive "one-liner" to update your system, install SSH for phone access, and deploy the Docker engine all at once:

bash
sudo apt update && sudo apt upgrade -y && sudo apt install openssh-server curl git -y && curl -fsSL [https://get.docker.com](https://get.docker.com) -o get-docker.sh && sudo sh get-docker.sh

---

Phase 2: Management & Remote Access
Copy and paste this block to deploy Portainer (Web UI) and Tailscale (VPN). This allows you to manage everything from your phone (using Termius and a browser) from anywhere in the world:

docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data portainer/portainer-ce:latest

# 2. Install Tailscale for Global Access
curl -fsSL [https://tailscale.com/install.sh](https://tailscale.com/install.sh) | sh
sudo tailscale up
