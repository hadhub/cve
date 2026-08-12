# Vulnerabilities

> CVEs, exploitand security advisories
> by [had](https://www.linkedin.com/in/hadrien-c/), [hadrien.cat](https://hadrien.cat/)

## 2026

| Folder | Target |
|--------|--------|
| [CVE-2026-27639-Mercator-XSS](CVE-2026-27639-Mercator-XSS/) | Mercator |
| [CVE-2026-49344-Mercator-JSON-DSL](CVE-2026-49344-Mercator-JSON-DSL/) | Mercator |
| [CVE-2026-49345-Mercator-SSRF](CVE-2026-49345-Mercator-SSRF/) | Mercator |

**CVE-2026-27639** - Stored XSS
Stored XSS -> forced password change on the default `admin` account, or privilege escalation of a malicious user to Admin
[Full write-up](https://hadrien.cat/posts/mercator-account-takeover) | [PoCs](CVE-2026-27639-Mercator-XSS/) | [Advisory](https://github.com/dbarzin/mercator/security/advisories/GHSA-65p7-pph2-966g) | [CVE record](https://www.cve.org/CVERecord?id=CVE-2026-27639)

**CVE-2026-49344** - JSON DSL query engine PII disclosure
Crafted JSON DSL query against Mercator's query engine -> dump of personally identifiable information (PII)
[Full write-up](https://hadrien.cat/posts/pii_leak_mercator/) | [PoC](CVE-2026-49344-Mercator-JSON-DSL/) | [Advisory](https://github.com/dbarzin/mercator/security/advisories/GHSA-q3r8-3h7c-96w3) | [CVE record](https://www.cve.org/CVERecord?id=CVE-2026-49344)

**CVE-2026-49345** - Server-Side Request Forgery
SSRF via the `gopher`/`telnet` scheme -> internal network port scan, or -> reachable internal Redis instance -> webshell write via `CONFIG SET` / `SAVE` -> RCE
[Full write-up](https://hadrien.cat/posts/ssrf_mercator/) | [PoCs](CVE-2026-49345-Mercator-SSRF/) | [Advisory](https://github.com/dbarzin/mercator/security/advisories/GHSA-6q97-4q5r-96j6) | [CVE record](https://www.cve.org/CVERecord?id=CVE-2026-49345)
