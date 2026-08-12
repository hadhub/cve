# Vulnerabilities

> CVEs, exploitand security advisories
> by [had](https://www.linkedin.com/in/hadrien-c/), [hadrien.cat](https://hadrien.cat/)

## 2026

| Folder | Target | Type |
|--------|--------|------|
| [CVE-2026-27639-Mercator-XSS](CVE-2026-27639-Mercator-XSS/) | Mercator | Stored XSS -> Account Takeover / Privilege Escalation (2 PoCs) |
| [CVE-2026-49344-Mercator-JSON-DSL](CVE-2026-49344-Mercator-JSON-DSL/) | Mercator | JSON DSL query engine abuse -> PII leak |
| [CVE-2026-49345-Mercator-SSRF](CVE-2026-49345-Mercator-SSRF/) | Mercator | SSRF -> internal port scan / Redis RCE (2 PoCs) |

**CVE-2026-27639** - Stored XSS
-> Chain: stored XSS -> forced password change on the default `admin` account, or privilege escalation of a malicious user to Admin
-> [Full write-up](https://hadrien.cat/posts/mercator-account-takeover) · [Advisory](https://github.com/dbarzin/mercator/security/advisories/GHSA-65p7-pph2-966g) · [CVE record](https://www.cve.org/CVERecord?id=CVE-2026-27639)
-> [PoCs](CVE-2026-27639-Mercator-XSS/)

**CVE-2026-49344** - JSON DSL query engine PII disclosure
-> Chain: crafted JSON DSL query against Mercator's query engine -> dump of personally identifiable information (PII)
-> [PoC](CVE-2026-49344-Mercator-JSON-DSL/query_engine_dump.py)

**CVE-2026-49345** - Server-Side Request Forgery
-> Chain: SSRF via the `gopher`/`telnet` scheme -> internal network port scan, or -> reachable internal Redis instance -> webshell write via `CONFIG SET` / `SAVE` -> RCE
-> [Port scan PoC](CVE-2026-49345-Mercator-SSRF/ssrf2scan.py) · [RCE PoC](CVE-2026-49345-Mercator-SSRF/ssrf2rce.py) · [Lab reset script](CVE-2026-49345-Mercator-SSRF/reset-lab.sh)
