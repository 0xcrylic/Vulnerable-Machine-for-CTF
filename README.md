```markdown
# 🎭 Port-Scan-Troll  
> A pre-built Ubuntu 22.04 VM that answers **“OPEN”** on **every TCP port** (1-65 530) – except the two you actually need.  
Perfect for CTFs, red-team labs, or just driving your friends’ nmap scripts insane.

---

## 🚀 TL;DR
1. Download the `.ova` → [Google Drive](https://drive.google.com/file/d/1UZE8CGTaF2Kq0gCwC2DmZiTwHJ6pcWJl/view?usp=sharing)  
2. Import into VMware / VirtualBox  
3. `nmap -p- <IP>` → watch 65 530 “open” ports appear 😈

---

## 📦 What’s inside
| Component | Details |
|-----------|---------|
| OS | Ubuntu 22.04.4 server (2 GB RAM, 20 GB disk) |
| Real services | 9090 Apache (`Server: httb`)<br>65530 OpenSSH (`SSH-2.0-OpenSSH_8.9p1 Ubuntu-3`) |
| Everything else | iptables REDIRECT → dummy listener on 8888 (silent drop) |
| Autostart | systemd units + persistent iptables rules |
| Image size | ≈ 1.8 GB `.ova` |

---

## 🔍 Quick test
```bash
# from any attacker box
nmap -p- --min-rate 1000 <VM_IP>
masscan <VM_IP> -p1-65535 --rate 10000
```

---

## ⚖️ Legal / ethical
Intended for **your own lab, CTF, or authorized pentest**.  
Do **NOT** expose this VM to the public internet – it will gladly chat with every scanner on the planet.

---

## 📜 License
MIT – scripts, configs, and the `.ova` itself. Hack, share, remix.

---

## 🤝 Contributing
Found a bug or want extra troll levels?  
PRs welcome at [GitHub](https://github.com/0xcrylic/Vulnerable-Machine-for-CTF) · Ping me on [LinkedIn](https://linkedin.com/in/astersec)
