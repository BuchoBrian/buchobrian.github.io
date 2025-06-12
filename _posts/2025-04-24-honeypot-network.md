---
title: "Honeypot Network Project"
date: 2025-06-11
collection: 
  - cybersecurity
tags: 
  - honeypot
  - logging
  - cowrie
  - alerts
  - threat-analysis
layout: single
author_profile: true
read_time: true
---

## 🎯 Project Overview

This project sets up a multi-service honeypot network designed to capture, log, and analyze real-world attack traffic. It includes **SSH**, **FTP**, **Telnet**, and **HTTP** honeypots running in isolated containers, backed by an automated alert system that sends summaries via email.

---

## 🧰 Components

### 🔐 SSH Honeypot
- Based on **Cowrie**, simulates a fake shell.
- Captures login attempts, password guesses, and attacker commands.

### 📂 FTP Honeypot
- Simulates a public FTP server.
- Logs anonymous login attempts, upload/download activity.

### 🖥 Telnet Honeypot
- Lightweight Telnet listener.
- Captures input and connection metadata from scanners.

### 🌐 HTTP Honeypot
- Mimics an unprotected web server.
- Logs access to fake admin panels, vulnerable endpoints, and default pages.

---

## 📬 Email Alert System

A custom Python script runs on a cron schedule, parsing the latest logs and sending:
- 📌 IP addresses & geolocation
- 📌 Command summaries
- 📌 Service targeted
- 📌 Timestamps of activity

The alerts give me a near real-time understanding of what services are being probed and how often.

---

## 📊 Sample Insights

> _Between May and June, the honeypots logged over **3,200** brute-force attempts, mostly targeting SSH and FTP. HTTP honeypot logs revealed bot traffic probing for WordPress login pages and outdated PHPMyAdmin panels._

---

## 🖼 Screenshots / Visuals

*Coming soon — terminal logs, dashboards, and email summaries.*

---

## 🔗 Related Resources

- [Cowrie SSH Honeypot](https://github.com/cowrie/cowrie)
- [Dionaea & Glastopf](https://github.com/mushorg)
- [ELK Stack for Visualization](https://www.elastic.co/elk-stack)

---

## 🤖 Next Steps

- Add Suricata for real-time threat detection
- Push logs to a central SIEM
- Enrich alerts with abuse IPDB and GeoIP

---

Want to deploy something similar? Let me know — I’d be happy to share the setup or scripts used.

