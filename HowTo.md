## NOTE: this process is practically the same for blocking bad domain names, but there is an extra step with domains (adding blacklist to dns filter).
just replace blacklist.txt with domainsblacklist.txt (`and IMPORTANT: URLs!`) when configuring the threat intelligence feed, and create a 'domain' feed, istead of 'IP'.
Also, be sure to add the feed you've created for domains to your DNS filter/policies 😊

## 🔧 How to Configure in FortiGate (Step-by-Step)

### 1. 📥 Add External Threat Feed

1. Log in to the **FortiGate GUI**
2. Go to **Security Fabric** → **External Connectors**
3. Click **Create New** → **Threat Feed**
4. Choose **Type**: `IP Address` *(or `Domain`, depending on your feed)*
5. **Feed URL**: Paste your raw GitHub link [blacklist.txt](https://raw.githubusercontent.com/osmiumostrich/Threat_Intelligence_Feeds/refs/heads/main/blacklist.txt) OR [domainsblacklist.txt](https://raw.githubusercontent.com/osmiumostrich/Threat_Intelligence_Feeds/refs/heads/main/domainsblacklist.txt)
7. Set **Refresh Interval**: e.g., every `60` minutes
8. Enable **Status** and save the connector

---

### 2. 🔐 Create an Address Object (Auto-created)

FortiGate will automatically create an **address object** named after your threat feed (e.g., `External-Resource-1` or `github-blacklist`).

You can use this object in firewall policies just like any other address.

---

### 3. 🚫 Create a Deny Firewall Policy

1. Go to **Policy & Objects** → **IPv4 Policy**
2. Click **Create New**
3. Set:
   - **Name**: `Block Threat Feed`
   - **Source**: `all` *(or restrict to internal IPs)*
   - **Destination**: your threat feed address object
   - **Service**: `ALL`
   - **Action**: `Deny`
   - **Log Violation Traffic**: ✅ enabled
4. Move the policy to the **top of the rule list**
5. Click **OK** to save

---
### 4. 🌐 How to configure the DNS filter for blocking Domains with the domainsblacklist.txt file.
Note: See step 1 for configuring the external threat feed connector before proceeding.
1. Navigate to `Security Profiles` Then `DNS Filter`
2. Open the **Default DNS filter** or `Create New`
3. Turn on **Category Based Filtering**.
4. Scroll down until you see a category called `Remote Categories`
5. You should see your threat feed address object that you created earlier.
6. Change the category to `Redirect to Block Portal`
Note: You must have DNS filtering enabled & applied to a firewall poclicy, if you don't have this the threat feed is useless!
---
