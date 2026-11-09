---
name: security-hardening
description: Fix vulnerabilities like an attacker and prove it like an auditor: attack-surface inventory, OWASP-minded sweep, risk-ranked patches, re-attack evidence.
category: frontend-craft
---

# security-hardening — افحص كخاطئ، أصلح كمهندس، أثبت كمدّقق

Load this for ANY security task: «أصلح الثغرات»، «اقفل الموقع»، «راجع الأمان»، «هنا SQL injection»، or when you inherit an app touching user data, auth, payments, or an exposed port. The method is an attacker-minded inventory → risk-ranked fixes → re-verification. ONE spirit rule: no security claim you did not VERIFY ships.

## Phase 1 — The attack-surface inventory (what exists before what's wrong)

Map the app in one list:
- ENTRY POINTS: every route/endpoint/form/query param, file-upload path, and any place user input enters.
- SECRETS & AUTH: where keys/tokens live (grep for hardcoded secrets, .env exposure, client-side key leaks), how sessions are issued/validated, admin boundaries.
- DATA FLOWS: what user input reaches a database query, a shell, an HTML page, a file path, a URL redirect.
- EXPOSURE: listening ports, CORS policy, dependency list (npm audit / pip audit via run_command — real output, not assumed).

## Phase 2 — The vulnerability sweep (OWASP-minded, code-level)

For each entry point, check the classic families in order of exploitability:
1. INJECTION (SQL/NoSQL/command): any string-concatenated query or shell call — parameterized statements / ORM bindings everywhere; NO exceptions for «quick internal» code.
2. XSS: every place user-or-DB content hits the DOM — context-aware escaping (HTML body, attribute, JS string, URL are DIFFERENT escapes); innerHTML with raw interpolation is the bug you will find most.
3. AUTH & ACCESS CONTROL: IDOR (object references trusting the request — /api/invoices/17 readable by user B), missing checks on admin routes, session fixation, tokens without expiry.
4. CSRF: state-changing endpoints without CSRF tokens/SameSite cookies.
5. SECRETS & CONFIG: .env served statically, source-maps shipping keys, debug endpoints in production, directory listing, default credentials.
6. DEPENDENCIES: audit output read; known-CVE packages upgraded or pinned-safe (report what actually blocks an upgrade).
7. HEADERS (when you control serving): CSP, X-Frame-Options/frame-ancestors, HSTS (HTTPS only), Referrer-Policy — a short real header set, tested, not a copy-paste wall.

## Phase 3 — Fix in risk order (and say the order)

CRITICAL (remote code exec / auth bypass / injected data at rest) → HIGH (stored XSS, IDOR on money) → MEDIUM (reflected XSS, missing CSRF) → HARDENING (headers, cookies flags, rate limits). Fix each with the MINIMAL correct patch — security patches are the worst place to refactor enthusiastically (diffs stay reviewable).

## Phase 4 — Re-verify like an attacker (the proof loop)

- Re-run the exact attack through the app: craft the malicious input again (in a test copy), submit it via browser (browser_type into the real form), observe the RESULT — blocked/sanitized/400, not «لحظة، الكود يقول إنه محمي».
- For XSS: the payload lands as TEXT (visible, escaped), never executes (browser_eval checking no script ran / the DOM shows encoded entities).
- For injection: the query errors or returns nothing for the crafted input; the parameterized version still returns LEGIT rows (a fix that broke the feature is not a fix).
- For IDOR: the other user's request → 403.
- Attach the before/after evidence in the delivery.

## Rules
- NEVER leave a found vulnerability «مؤجل» silently — it goes in the delivery as OPEN with severity and why.
- No fabricated CVE numbers or invented scanner results — cite what you actually ran (the audit command's real output).
- When the fix needs an architectural change beyond the session's scope: ship the protective stopgap (input rejection, route disable) + the honest recommendation.
- Secrets found in code: they are already compromised — rotate them (tell the user plainly), THEN remove from source into .env.

## Done when
The inventory exists, every family was actually CHECKED (not skimmed), fixes are risk-ranked and minimally patched, every fixed item has re-attack evidence, dependencies audited with real output, and the delivery separates FIXED / OPEN / RECOMMENDED honestly.
