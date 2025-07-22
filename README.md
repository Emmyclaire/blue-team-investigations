# blue-team-investigations
SOC-style alert investigations, detection analysis, and Blue Team learning labs by TraceHuntress
# 🧪 Alert 001: Excessive Failed Logins on SSH Server

**Date:** July 2025  
**Analyst:** TraceHuntress  
**Alert Source:** SIEM (Security Onion / Wazuh)

---

## 🚨 Alert Summary
A detection rule triggered due to over 10 failed login attempts within a short time from a single IP address on port 22 (SSH).

---

## 🔎 Initial Investigation
- Reviewed logs from `/var/log/auth.log`
- Source IP: `198.51.100.42` (Unknown location)
- Time window: Between 2:03 AM – 2:08 AM
- Brute-force behavior observed
- No successful login detected

---

## 🛡️ Action Taken
- Added IP to firewall blocklist
- Checked for existing compromise — nothing found
- Enabled fail2ban to reduce future brute-force attempts
- Alerted system admin

---

## 🧠 Lessons Learned
- Need to tighten SSH configurations
- Add GeoIP alerts for unusual regions
- Consider multi-factor auth (MFA)

---

## 🔧 MITRE ATT&CK Reference
- **Technique:** Brute Force (T1110)
- **Tactic:** Credential Access

---

> “Every failed login could be a whisper of something louder coming.”
