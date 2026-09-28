# 📄 Project Documentation: Phishing Simulation Using GoPhish on AWS EC2

This document walks through the technical execution of the phishing simulation, referencing evidence collected at each stage of the engagement. All screenshots referenced below are stored in the [`/evidence`](./evidence) folder.

---

## 1. Infrastructure Deployment (AWS EC2)

The GoPhish binary was deployed and launched on an Ubuntu-based AWS EC2 instance. The terminal output below confirms a successful startup: the admin server binding to port `3333`, the phishing server binding to port `8080`, and the initial auto-generated admin credentials.

**Evidence:** `evidence/06-ec2-terminal-gophish-running.jpg`

Key details captured in this step:
- GoPhish started the admin interface at `https://0.0.0.0:3333`
- The public phishing server started at `http://0.0.0.0:8080`
- Live request logs show real inbound traffic from a target's IP hitting the login page and associated static assets (CSS/JS/images), confirming the landing page rendered correctly

> ⚠️ Kindly Note: The auto-generated admin password shown in the raw terminal log has since been rotated and is not valid credential material.

---

## 2. Admin Console Access

Once the service was running, the GoPhish admin login portal was accessed over HTTPS on port `3333`.

**Evidence:** `evidence/05-gophish-admin-login.jpg`

This confirms the admin panel was reachable and secured behind authentication before any campaign configuration began.

---

## 3. Landing Page Configuration

A cloned Microsoft-style login page was imported into GoPhish's landing page editor as the credential capture surface for the campaign.

**Evidence:** `evidence/04-landing-page-editor.jpg`

Configuration details:
- Page name: `mymicrosoft landing page`
- HTML sourced via the **Import Site** feature to replicate a realistic Microsoft Online Services sign-in page
- **Capture Submitted Data** enabled to log form submissions
- **Capture Passwords** intentionally left disabled in this pass, and GoPhish's built-in warning that captured credentials are stored as cleartext when this option is used was noted for handling procedures

---

## 4. Campaign Dashboard & Monitoring

The GoPhish dashboard was used to track live campaign metrics in real time across all launched campaigns.

**Evidence:** `evidence/01-gophish-dashboard.jpg`

The dashboard displays five key funnel metrics per campaign:
| Metric | Description |
|---|---|
| Email Sent | Total phishing emails dispatched |
| Email Opened | Recipients who opened the email |
| Clicked Link | Recipients who clicked the phishing link |
| Submitted Data | Recipients who submitted data on the landing page |
| Email Reported | Recipients who reported the email as suspicious |

A time-series "Phishing Success Overview" chart also visualizes the cumulative success rate as the campaign progressed, showing a clear upward trend as users clicked through and submitted data.

---

## 5. Campaign Results Summary

Campaign-level results were reviewed from the "Recent Campaigns" table, showing per-campaign totals and status.

**Evidence:** `evidence/02-campaign-results.jpg`

Example campaign (`micorsoft`): 3 emails sent, in-progress status at time of capture, with click and submission counts tracked live per recipient.

---

## 6. Individual Target Timeline & Data Capture

GoPhish logs a per-recipient event timeline, capturing the exact sequence and timestamps of link clicks and data submission, along with device/browser fingerprinting (OS and browser version) for each event.

**Evidence:** `evidence/03-captured-data-timeline.jpg`

This view demonstrates:
- Multi-device engagement from a single recipient (Windows/Chrome, then Android/Chrome)
- A "Submitted Data" event with parameter-level detail of the form fields captured
- The built-in **Replay Credentials** feature, which allows the tester to validate captured input against the real service (used here only to confirm form-field mapping, not for unauthorized account access)

> 🔒 **Handling note:** Captured form values (including the test credential shown in this view) are simulation artifacts from a controlled test account, not real production credentials, and have been excluded from this write-up. Any real captured data collected during an engagement should be treated as sensitive, stored encrypted, and purged per the engagement's data handling agreement.

---

## Summary of Evidence Files

| File | Description |
|---|---|
| `01-gophish-dashboard.jpg` | Live dashboard with funnel metrics and success-rate chart |
| `02-campaign-results.jpg` | Recent campaigns summary table |
| `03-captured-data-timeline.jpg` | Per-target event timeline and submitted data detail |
| `04-landing-page-editor.jpg` | Cloned landing page HTML import and capture settings |
| `05-gophish-admin-login.jpg` | GoPhish admin authentication portal |
| `06-ec2-terminal-gophish-running.jpg` | EC2 terminal output showing GoPhish startup and live request logs |
