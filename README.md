# Fake reCAPTCHA Phishing Landing Page

This proof-of-concept demonstrates how an iframeable website with missing X-Frame-Options or Content-Security-Policy: frame-ancestors can be abused to create a realistic phishing landing page. I saw a bunch of phishing scams and people were actually falling for this technique, so I reverse engineered the landing and created a better one for use in pentesting.

![fake-reCAPTCHA](https://github.com/user-attachments/assets/448445c0-bba6-4aa5-94f3-2d9f23fbf0c0)




The page displays a fake reCAPTCHA modal over a legitimate target website embedded in the background using a full-screen iframe. It simulates a verification prompt and tricks the user into copying and running a PowerShell command via a clipboard payload. Mobile users are shown a mock IT error screen to simulate device restrictions and force access from a desktop environment.

- Demonstrates the risk of clickjacking and UI redress attacks
- Highlights how iframe embedding can boost the credibility of phishing pages
- Useful for red team or awareness demos

## Steps
1) Create a powershell script and encode it as base64 (use [https://github.com/securekomodo/psencode](https://github.com/securekomodo/psencode) utility to convert your PS to base64 using Python.
<img width="525" alt="image" src="https://github.com/user-attachments/assets/94168d84-20ed-4ac2-9dc2-ee25776c71bf" />

Cleartext Payload: `Start-Process "calc.exe"`

Encoded Payload: UwB0AGEAcgB0AC0AUAByAG8AYwBlAHMAcwAgACIAYwBhAGwAYwAuAGUAeABlACIACgA=

3) Update the webpage with your payload (note, keep it short for a stager as longer strings may be truncated)
4) Update the webpage with the background iframe, or leave it empty for a standard gray background.

![powershell-reCAPTCHA](https://github.com/user-attachments/assets/c822e0f9-9b60-4c9d-942a-fe49b57474a9)

This PoC is for educational and authorized testing only. Do not deploy or distribute in unauthorized environments.
