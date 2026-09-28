# 🎣 PhishGuard: Phishing Simulation & Security Awareness Assessment

**Simulating real-world social engineering attacks to measure — and improve — human resilience.**

An authorised, end-to-end phishing simulation built on **AWS EC2** and **GoPhish**, designed to evaluate user susceptibility to social engineering and assess the effectiveness of an organisation's security awareness controls.

---

## 📌 Overview

Technical controls only go so far — humans remain the most exploited attack vector in modern breaches. This project simulates a realistic phishing campaign in a controlled, ethical environment to quantify that risk and generate actionable recommendations.

**Key outcomes:** delivery, click-through, and credential submission rates were tracked end-to-end, revealing clear behavioural patterns tied to urgency and brand familiarity.

---

## 🎯 Objectives

- Simulate a realistic phishing attack in a controlled environment
- Measure user interaction with phishing emails (opens, clicks, submissions)
- Demonstrate practical skills in ethical social engineering testing and cloud-based security infrastructure

---

## 🛠️ Tech Stack

| Component | Purpose |
|---|---|
| **AWS EC2** | Cloud-hosted phishing infrastructure |
| **GoPhish** | Campaign management, tracking, and reporting |
| **Security Groups** | Network access control (HTTP/80, SSH/22) |
| **Custom Landing Page** | Credential capture simulation |
| **Email Templates** | Realistic organisational-style lures |

---

## 🏗️ Methodology

### 1. Infrastructure Setup
- Provisioned an AWS EC2 instance with appropriate compute and network settings
- Configured security groups to allow only required services (HTTP/80, SSH/22)
- Installed and securely configured the GoPhish framework

### 2. Campaign Design
- Configured sender profile and campaign parameters within GoPhish
- Built a phishing landing page to capture user interaction data
- Crafted a realistic phishing email template mimicking common organisational communication styles

### 3. Campaign Execution
- Launched the phishing campaign in a controlled environment
- Monitored email delivery and server performance in real time
- Tracked user engagement metrics live via the GoPhish dashboard

### 4. Data Collection
- Email delivery success rate
- Link click-through rate
- Credential submission capture rate

---

## 🧠 Key Findings

- 📈 Click-through behaviour indicated strong susceptibility to **urgency-based messaging**
- 🏢 Users were more likely to interact with emails closely resembling **legitimate, familiar entities**
- 👤 **Human factors remain a significant attack vector**, even where technical controls are in place

---

## ✅ Recommendations

- **Security Awareness Training** — recurring, scenario-based training tied to real observed behaviours
- **Email Authentication Controls** — enforce **SPF, DKIM, and DMARC** to reduce spoofing risk

---

## 🤹 Skills Demonstrated

- Ethical phishing simulation & social engineering assessment
- GoPhish campaign design and management
- AWS EC2 provisioning and secure configuration
- Security awareness evaluation and reporting

---

## 📋 Conclusion

This project demonstrates the practical execution of an ethical phishing simulation using GoPhish deployed on AWS EC2. It highlights the persistent risk posed by social engineering and reinforces that resilient organisations pair strong technical controls with continuous, evidence-driven user education.

---

## ⚠️ Ethical Disclaimer

This simulation was conducted with **proper authorisation** in a controlled environment for educational and assessment purposes only. No real user data was compromised, and results were used exclusively to inform security awareness improvements. Unauthorised phishing activity is illegal — always obtain explicit written consent before conducting any simulated social engineering exercise.

---

## 📬 Contact

Questions, feedback, or collaboration ideas? Feel free to reach out or open an issue.
