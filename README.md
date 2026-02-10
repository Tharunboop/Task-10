
# Task 10 – Firewall Configuration & Testing

## Cyber Security Internship  
**Task Name:** Firewall Configuration & Testing  
**Operating System:** Kali Linux  
**Firewall Tool:** UFW (Uncomplicated Firewall)

---

## 📌 Objective

The objective of this task is to configure and test a firewall using UFW on Kali Linux.  
The task demonstrates the ability to:
- Configure firewall rules
- Allow and deny network ports
- Enable firewall logging
- Block a malicious IP address
- Test allowed and blocked traffic
- Observe firewall logs
- Document firewall behavior and impact

---

## 🛠 Tools Used

- **UFW (Uncomplicated Firewall)**
- Terminal (Kali Linux)
- journalctl (for log monitoring)
- ping, nmap (for testing)

---

## 🔹 Step 1: UFW Installation

UFW was installed using the APT package manager.

```bash
sudo apt update
sudo apt install ufw -y
````


---

## 🔹 Step 2: Initial Firewall Status

After installation, UFW is inactive by default on Kali Linux.

```bash
sudo ufw status
```


---

## 🔹 Step 3: Configure Default Rules

Default firewall policies were set to enhance security.

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

* Incoming traffic is blocked by default
* Outgoing traffic is allowed

---

## 🔹 Step 4: Allow Required Ports

Essential ports were allowed to enable normal services.

```bash
sudo ufw allow ssh
sudo ufw allow 80
sudo ufw allow 443
```


---

## 🔹 Step 5: Deny a Port (FTP)

FTP port (21) was blocked to demonstrate port-level restriction.

```bash
sudo ufw deny 21
```



---

## 🔹 Step 6: Enable Firewall

The firewall was enabled and configured to start automatically on boot.

```bash
sudo ufw enable
```



---

## 🔹 Step 7: Enable and Verify Logging

Firewall logging was enabled to monitor allowed and blocked traffic.

```bash
sudo ufw logging on
sudo ufw status verbose
```



---

## 🔹 Step 8: Observe Firewall Logs (Kali Linux)

On Kali Linux, UFW logs are managed by **systemd** instead of `/var/log/ufw.log`.

Logs were observed using:

```bash
sudo journalctl -xe | grep -i ufw
```

Blocked traffic entries (`[UFW BLOCK]`) were successfully identified.



---

## 🔹 Step 9: Block a Malicious IP Address

A sample malicious IP address was blocked to prevent unauthorized access.

```bash
sudo ufw deny from 192.168.1.100
sudo ufw status numbered
```


---

## 🔹 Step 10: Test Connectivity

### ✅ Allowed Traffic Test


This confirms outgoing traffic is allowed.


---

### ❌ Blocked Traffic Test

Blocked ports were tested using Nmap.

```bash
sudo nmap localhost
```

FTP port (21) appears as closed/filtered.

---

## 📊 Firewall Rules Summary

| Rule Type        | Details                          |
| ---------------- | -------------------------------- |
| Default Incoming | Deny                             |
| Default Outgoing | Allow                            |
| Allowed Ports    | 22 (SSH), 80 (HTTP), 443 (HTTPS) |
| Blocked Port     | 21 (FTP)                         |
| Blocked IP       | 192.168.1.100                    |
| Logging          | Enabled                          |

---

## 🎯 Final Outcome

* Successfully configured firewall rules
* Reduced system attack surface
* Verified allowed and blocked traffic
* Observed firewall logs
* Gained hands-on firewall management experience

---

## ✅ Conclusion

This task demonstrates practical firewall configuration and testing skills using UFW on Kali Linux.
All task requirements were completed successfully with proper documentation and verification.


✅ **Task Completed Successfully**


## Final Outcome
- Configured firewall rules successfully
- Allowed and blocked ports verified
- Logging enabled and observed
- Malicious IP blocked
- Firewall management skills gained
