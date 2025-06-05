# 🛡️ Custom Threat Intelligence Feed for FortiGate

Welcome to your custom threat feed! This repository hosts plain text files (`blacklist.txt`) & (`domainsblacklist.txt`) containing malicious IP addresses, and domain names that you want to block at your firewall.

This feed is designed to be **used directly by FortiGate firewalls** via the External Threat Feed feature. Once configured, FortiGate will **pull the file on a regular interval** and automatically block traffic to any destination listed in the feed.
---
📑 Link to how to guide! 🔗 https://github.com/osmiumostrich/ArrowForce_Threat_Intelligence_Feeds/blob/main/HowTo.md
---

## 📄 Contents

- `blacklist.txt` — the list of IPs to block (one per line)
- `README.md` — documentation and setup guide (this file)
- `domainsblacklist.txt` - the list of domains to block (one per line)

## 🌐 Feed URLs

## 🔗 https://github.com/osmiumostrich/ArrowForce_Threat_Intelligence_Feeds/blob/main/blacklist.txt
## 🔗 https://github.com/osmiumostrich/ArrowForce_Threat_Intelligence_Feeds/blob/main/domainsblacklist.txt
