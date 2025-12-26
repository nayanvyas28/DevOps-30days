# Day 02 – Linux Deep Dive (DevOps Essentials)

## Package Management (apt)
Package managers are used to install, update, and remove software.

Common commands:
- sudo apt update                   
- sudo apt upgrade
- sudo apt install <package>
- sudo apt remove <package>

Example:
sudo apt install nginx

---

## What are Services?
Services are background programs that run automatically.

Examples:
- nginx (web server)
- docker
- ssh

---

## systemctl (Service Manager)
systemctl is used to manage services in Linux.

Common commands:
- systemctl status <service>
- systemctl start <service>
- systemctl stop <service>
- systemctl restart <service>
- systemctl enable <service>
- systemctl disable <service>

Example:
sudo systemctl start nginx
sudo systemctl enable nginx

---

## Logs in Linux
Logs help diagnose issues and failures.

Important log locations:
- /var/log/syslog
- /var/log/auth.log
- /var/log/nginx/

Commands:
- tail -f /var/log/syslog
- journalctl
- journalctl -u nginx

---

## Environment Variables
Used to store configuration values.

Commands:
- echo $PATH
- env
- export APP_ENV=production

Environment variables are heavily used in DevOps & CI/CD.

---

## Networking Basics
Used to test connectivity and ports.

Commands:
- ping
- curl
- wget
- netstat -tulnp
- ss -tulnp

---

## Firewall Basics (ufw)
Firewall controls incoming and outgoing traffic.

Commands:
- sudo ufw status
- sudo ufw allow 80
- sudo ufw enable

---

## What I Learned Today
- Installing software using apt
- Managing services using systemctl
- Reading logs for debugging
- Understanding environment variables
- Basic networking and firewall concepts

---

## Interview Notes
- Services run in background
- Logs are stored in /var/log
- systemctl controls services
- Environment variables are key-value pairs
