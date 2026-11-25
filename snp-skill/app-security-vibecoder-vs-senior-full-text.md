# Your App's Security, Vibecoder vs Senior Dev
Text from the video, recorded 2026-11-25.

1. Key in the frontend / Server-side env var
Server-side env variable with .env gitignored. No API keys in frontend env vars

2. Installs anything / Checks npm first
AI invents up to 6.1% of package names

3. Runs any command / Permission prompts on
Default permissions. Bypass mode only in a container

4. Tests as himself / RLS + 2nd account
RLS on every table, tested with a second account. Number 1 risk: broken access control, OWASP 2025

5. Homemade login / Proven auth
Never roll your own auth. Supabase Auth or Clerk. Use a premade, well-trusted auth system, OWASP 2025

6. Waits for users / Sentry + alerts
Sentry on errors, alerts on failed login spikes. Average data breach: $4.99M, IBM 2026

7. Untested backups / Restore tested
Point in time recovery, and I've tested a restore. 5 backup methods, none worked, GitLab 2017

8. Ships first draft / /security-review
Finds SQL injection, XSS, auth flaws

Closing line: Which means the gap isn't IQ, it's 8 prompts. Screenshot this list and paste it into Claude.
