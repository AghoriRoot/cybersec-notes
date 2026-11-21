# Day 1: Offensive vs Defensive Security + First Lab

Date: 22 Nov 2026
Platform: TryHackMe
Status: ✅ Completed

## 📌 Summary
Today I learned the difference between offensive and defensive security,
used the terminal for the first time in a lab, and exploited a broken
access control flaw in a simulated bank application.

## 🔑 What I Learned

### Offensive Security (Red Team)
- Think like an attacker and find weaknesses before real attackers do
- Examples: penetration testing, vulnerability research, red teaming

### Defensive Security (Blue Team)
- Protect systems, detect attacks, and respond to incidents
- Examples: monitoring, SIEM, incident response, hardening

### Key Difference
Offensive security asks *"How can this be broken?"*
Defensive security asks *"How do we stop and detect it?"*
Both are needed. Attackers find the gaps, defenders close them.

## 🧪 Practical: Simulated Bank Lab
1. Opened the terminal in the TryHackMe simulated desktop and ran my first commands
2. dirb (Wordlist se hidden web directories dhundne ka tool)
3. Explored the target web app and discovered a "hidden admin panel"
4. Used account number `8881` to deposit $2000 through the admin page
5. Confirmed the balance turned positive and captured the flag

## 🐞 Vulnerability Found
Broken Access Control / Insecure Direct Object Reference (IDOR)
The admin page had no proper authorization check, so anyone who found the URL could add money to an account.

## 🛡️ How to Fix It
- Require authentication and role checks (admin only) on every admin route
- Never rely on "hidden" URLs for security (security through obscurity)
- Validate every request on the server side
- Log and monitor admin actions

## ❓ Doubts
- How do real companies detect unauthorized admin access?

## ✅ Takeaway
A hidden page is not a protected page. Access must be enforced by the server, not by hiding links.

> ⚠️ All activity was performed in a legal TryHackMe lab environment for educational purposes only.
