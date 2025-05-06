# Fake reCAPTCHA Phishing Landing Page

![fake-reCAPTCHA](https://github.com/user-attachments/assets/448445c0-bba6-4aa5-94f3-2d9f23fbf0c0)


This proof-of-concept demonstrates how an iframeable website with missing X-Frame-Options or Content-Security-Policy: frame-ancestors can be abused to create a realistic phishing landing page.

The page displays a fake reCAPTCHA modal over a legitimate target website embedded in the background using a full-screen iframe. It simulates a verification prompt and tricks the user into copying and running a PowerShell command via a clipboard payload. Mobile users are shown a mock IT error screen to simulate device restrictions and force access from a desktop environment.

- Demonstrates the risk of clickjacking and UI redress attacks
- Highlights how iframe embedding can boost the credibility of phishing pages
- Useful for red team or awareness demos

This PoC is for educational and authorized testing only. Do not deploy or distribute in unauthorized environments.
