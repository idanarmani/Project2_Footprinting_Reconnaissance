# Project 2: Footprinting & Reconnaissance

A hands-on cybersecurity reconnaissance project covering passive OSINT, DNS/WHOIS footprinting, email/subdomain harvesting, and local network discovery — using four different tools and techniques across Kali Linux and Windows.

## 📋 Overview

This project documents four modules of footprinting practice:

- **Module 1** — Passive footprinting of `networkwalks.com` using six built-in Kali Linux tools: `whois`, `whatweb`, `nslookup`, `curl`, `wafw00f`, and `dnsrecon`.
- **Module 3** — OSINT graphing with **Maltego** (installation and setup documented; account activation blocked by export-law country restrictions).
- **Module 4** — Email and subdomain harvesting against `microsoft.com` using **theHarvester**, across multiple public data sources.
- **Module 5** — Local network discovery using **Zenmap** (Nmap's GUI) to enumerate the local subnet, live hosts, open ports, and OS fingerprinting.

## 🛠️ Tools & Targets

| Module | Tool | Target |
|---|---|---|
| 1 | whois, whatweb, nslookup, curl, wafw00f, dnsrecon | networkwalks.com |
| 3 | Maltego CE | networkwalks.com |
| 4 | theHarvester | microsoft.com |
| 5 | Zenmap (Nmap GUI) | Local subnet (192.168.56.0/24) |

## 🔍 Key Findings

**Module 1:**
- Domain registered via GoDaddy (privacy-protected), created 2019, expires 2027.
- Web stack: Apache + WordPress 7.1 + jQuery 3.7.1.
- Site is protected by **ModSecurity (SpiderLabs) WAF**.
- Full DNS record enumeration via dnsrecon.

**Module 3:**
- Maltego and its Java (Eclipse Temurin JRE 17) dependency installed successfully.
- Account activation could not be completed — Maltego's registration flow explicitly blocks certain countries under export law. Documented with evidence rather than skipped.

**Module 4:**
- Baidu-only search (limit 1000): no results in theHarvester's parsed format — a valid, documented outcome.
- All-sources search (limit 50): 6 ASNs, 57 IPs, 3 email addresses, and **9,423 subdomains** discovered from public sources not requiring API keys.

**Module 5:**
- Identified local subnet as `192.168.56.0/24` (VirtualBox Host-Only network).
- Ping scan returned no hosts (ICMP often blocked); Intense scan (ARP-based) found 1 live host.
- Live host fingerprinted as Windows 11 24H2–25H2, with 5 open ports identified (RPC, NetBIOS, SMB, and two VMware Authentication Daemon ports).
- Network topology exported as PDF ([`topology.pdf`](./topology.pdf)).

## 📄 Full Report

See [`Project2_Footprinting_Reconnaissance_Report.pdf`](./Project2_Footprinting_Reconnaissance_Report.pdf) for the complete step-by-step writeup with all screenshots and evidence across all four modules.

## 📚 Related Work

- [Project 1: Kali Linux & Windows 10 VirtualBox Lab](../cybersecurity-lab-kali-virtualbox) — VM setup and NAT networking foundation this project builds on.

---
*This project is part of an ongoing internship program for cybersecurity and networking practice.*
