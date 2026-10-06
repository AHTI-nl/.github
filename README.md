# AHTI community health files

This public repository contains the default security policy for AHTI-nl repositories that do not supply their own `SECURITY.md`.

Report suspected vulnerabilities privately to **security@ahti.nl**. The full policy source is [Responsible Disclosure](docs/responsible-disclosure.md).

## Publishing the central policy

Publish `docs/responsible-disclosure.md` as `https://www.ahti.nl/responsible-disclosure`, using the AHTI website’s normal page styling. Publish `security/.well-known/security.txt` at `https://www.ahti.nl/.well-known/security.txt` over HTTPS with `Content-Type: text/plain; charset=utf-8`. No homepage link is required.

These files are publication sources; merging this repository does not deploy the AHTI website. Confirm both URLs return the intended content before merging dependent redirect PRs. The central URLs were not available during preparation on 6 October 2026.

Every public service hostname should serve its own `/.well-known/security.txt` or redirect to the central file. The central hostname alone does not cover subdomains. Existing CDN/load-balancer configuration is preferred; directly public application hosts need their own route or file. Keep protected origins protected.

The website owner must verify that the security mailbox is monitored and renew the `Expires` field before **1 October 2027**. Update any static copies on hosting services that cannot issue an HTTP redirect when changing the contact or expiration.

References: [RFC 9116](https://www.rfc-editor.org/rfc/rfc9116.html), [GitHub default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).
