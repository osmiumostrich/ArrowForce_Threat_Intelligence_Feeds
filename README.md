# 🛡️ Custom Threat Intelligence Feed for FortiGate

Welcome to your custom threat feed! This repository hosts a plain text file (`blacklist.txt`) containing malicious IP addresses, hostnames, or URLs that you want to block at your firewall.

This feed is designed to be **used directly by FortiGate firewalls** via the External Threat Feed feature. Once configured, FortiGate will **pull the file on a regular interval** and automatically block traffic to any destination listed in the feed.

---

## 📄 Contents

- `blacklist.txt` — the list of IPs, domains, or URLs to block (one per line)
- `README.md` — documentation and setup guide (this file)

---

## ✅ Features

- ✅ Supports IP addresses, domains, and URLs
- ✅ Pullable over HTTPS
- ✅ Fully compatible with FortiGate External Resources
- ✅ Version-controlled and easy to manage
- ✅ Simple to update and extend

---

## 🌐 Feed URL (for FortiGate)

> ⚠️ https://github.com/osmiumostrich/ArrowForce_Threat_Intelligence_Feeds/blob/main/blacklist.txt
