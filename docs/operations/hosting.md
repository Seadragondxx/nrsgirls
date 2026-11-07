# nrsgirls.com hosting and WordPress connection

Status reviewed: November 4, 2026. The owner has selected GoDaddy Managed WordPress for website hosting while retaining Cloudflare for DNS; the production domain connection is still pending.

## Service responsibilities

| Component | Provider | Status |
| --- | --- | --- |
| Domain registration | GoDaddy | Existing registration confirmed in the domain dashboard |
| Authoritative DNS | Cloudflare | GoDaddy identifies Cloudflare as the current DNS provider; retain the existing nameservers |
| Website hosting | GoDaddy Managed WordPress | Existing active hosting plan found; connection to nrsgirls.com is not yet verified |
| Content management | WordPress on GoDaddy | Intended website management location after connection and verification |
| Source and documentation | GitHub | This repository remains available for existing application code and operational documentation |

This is a hosting-only change, not a registrar transfer or nameserver migration. No DNS, hosting, WordPress content, or deployment configuration was changed during this documentation update.

The existing WordPress preview is [NRS Group of Fresno](https://484813.us22.myftpupload.com/), which displayed “Great things are coming soon” during the public-page check. Confirm that the intended content is ready, or obtain explicit approval to launch the placeholder, before pointing the production domain at it.

## Preconditions

- Confirm access to the Cloudflare account that owns the nrsgirls.com zone and the GoDaddy account with the existing WordPress installation.
- Inspect the WordPress site's domain connection screen and copy the exact required DNS targets. Do not infer the production target from the temporary preview hostname.
- Securely preserve the current DNS records, proxy states, TTLs, relevant routing rules, and WordPress backup information outside this public repository.
- Check for Cloudflare Workers routes, redirects, or other rules affecting the apex and www hostnames before switching traffic.
- Confirm the intended public content, existing email service, and any subdomains that must continue working.
- Obtain approval for the exact live changes after the current and proposed values are known.

## Connection checklist

- [ ] Inspect the current apex and www DNS records in Cloudflare.
- [ ] Record GoDaddy's required apex and www targets and domain-verification instructions.
- [ ] Preserve all unrelated records, especially mail routing and authentication records.
- [ ] Keep the existing Cloudflare nameservers and GoDaddy registration unchanged.
- [ ] Prepare the WordPress custom-domain association and review any warnings about automatic DNS or nameserver changes.
- [ ] Determine the appropriate proxy and TLS configuration from the hosting requirements; do not weaken TLS merely to bypass a connection error.
- [ ] Approve the precise change set and rollback plan.
- [ ] Apply only the approved website-related changes.
- [ ] Verify GoDaddy's domain and certificate status.
- [ ] Verify HTTPS, expected content, redirects, and the intended canonical hostname for both nrsgirls.com and www.nrsgirls.com.
- [ ] Verify WordPress administration and representative pages, media, forms, and links.
- [ ] Confirm unrelated subdomains and email still work.
- [ ] Replace this pending status with the verified completion date and a non-sensitive change summary.

## GitHub scope

The existing repository contains application scaffolding; it is not documented here as a WordPress deployment source. This documentation update does not convert the application to WordPress, migrate its content, or establish GitHub-to-WordPress deployment.

Do not disable workflows, remove existing hosting resources, change repository visibility, or delete application code as part of this documentation-only update. Any future code migration or deployment change needs its own reviewed scope.

## Rollback and handoff

If the new connection fails, restore the approved pre-change website DNS values and any routing or WordPress domain settings changed during the switch. Keep the previous hosting resources available until the new site has been validated.

Record the actual values and backup locations in an appropriately restricted operational record. Never commit passwords, API tokens, transfer codes, session cookies, account identifiers, or full DNS exports to this repository.
