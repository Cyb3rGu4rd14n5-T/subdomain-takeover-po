# subdomain-takeover-po
test 


# Subdomain Takeover Proof of Concept

## Vulnerability
ACT Fibernet's subdomain `elink.actcorp.in` is vulnerable to subdomain takeover via Cargo Collective.

## Proof of Concept
### Current State:
- `https://elink.actcorp.in` → Shows Cargo Collective 404 page
- DNS points to Cargo Collective servers
- No site configured → Available for claiming

### Attack Scenario:
An attacker could:
1. Sign up for Cargo Collective free account
2. Add `elink.actcorp.in` as custom domain
3. Host malicious content (phishing, malware, etc.)

### Demo:
[View PoC Page](https://yourusername.github.io/subdomain-takeover-poc/poc.html)

This mock phishing page demonstrates what could be hosted at the vulnerable subdomain.

## Evidence
1. **DNS Records:** `elink.actcorp.in` → CNAME to Cargo Collective
2. **404 Page:** Unconfigured Cargo Collective site
3. **Tool Output:** Subzy confirms vulnerability

## Impact
- Phishing attacks under trusted `actcorp.in` domain
- Cookie stealing via malicious JavaScript
- Brand reputation damage
- Potential internal network access (if used for SSO)

## Remediation
- Remove CNAME records pointing to third-party services
- Monitor subdomains for dangling DNS records
- Use services that require domain verification
