# 20 Ways Someone Hacks Your Vibecoded App
About 4,000 databases wiped. Text from the video, recorded 2026-11-25.

1. Next.js header
Login check skipped when it lives in Next.js middleware. CVSS 9.1 critical, GitHub Advisory, Mar 2025

2. .git folder
28,000 exposed .git repositories. 107 live Stripe secret keys recovered, Intruder, Aug 2026

3. Supabase storage
Public buckets: anyone who possesses the asset URL can readily access the file, Supabase docs

4. Price from the browser
Recalculate amounts on your server. Don't trust client-provided prices or totals, Stripe docs

5. Credential stuffing
19% of all login attempts were credential stuffing, median daily figure, Verizon DBIR 2025

6. Open database
About 74,000 open databases deleted by an automated script, BleepingComputer, Jul 2020

7. Polyfill.io
100K+ sites embedded cdn.polyfill.io, then caught injecting malware on mobile devices, Sansec, Jun 2024

8. SMS pumping
Your business pays for every message sent to those numbers, Twilio

9. Prompt injection
LLM01, Prompt injection, OWASP Top 10 for LLM apps, 2025

10. Weak JWT secret
It can be trivial for an attacker to brute-force a server's secret, PortSwigger

11. Race condition
Enables you to exceed some kind of limit imposed by the business logic, PortSwigger

12. Account pre-hijacking
35 of 75 popular services vulnerable to account pre-hijacking, at least, USENIX Security 2022

13. Subdomain takeover
4,000 of 16,000 dangling subdomains taken over, automatically, Silent Push, Jul 2026

14. SSRF
SSRF vulnerabilities allow attackers to make unauthorized requests from web applications. The metadata service makes the AWS credentials available, AWS Security Blog

15. Path traversal
Enable an attacker to read arbitrary files on the server. Apache, CVE-2021-41773: critical, PortSwigger

16. Reset poisoning
The password reset token will be delivered to the attacker's server, PortSwigger

17. Source maps
512,000+ lines of Claude Code readable from one source map, The Hacker News, Apr 2026

18. Clickjacking
By loading this page into an invisible iframe, an attacker could trick a user, OWASP

19. Open redirect
Create a hyperlink to redirect your users to an unvalidated malicious website, OWASP

20. User enumeration
An application should respond (both HTTP and HTML) in a generic manner. Different errors tell attackers which emails are real, OWASP Authentication Cheat Sheet

Closing line: Screenshot this list and paste it into Claude.
