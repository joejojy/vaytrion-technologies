# DNS Setup for GitHub Pages — www.vaytrion.com

## Provider

- Domain registrar: Squarespace
- Hosting: GitHub Pages
- Repository: joejojy/vaytrion-technologies

## Squarespace DNS Records

Navigate to: Squarespace > Domains > vaytrion.com > DNS Settings > Custom Records

### A Records (apex domain)

| Type | Host | Value           |
|------|------|-----------------| 
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |

### CNAME Record (www subdomain)

| Type  | Host | Value                |
|-------|------|----------------------|
| CNAME | www  | joejojy.github.io   |

## GitHub Pages Settings

1. Go to repository Settings > Pages
2. Source: GitHub Actions
3. Custom domain: www.vaytrion.com
4. Enforce HTTPS: Enabled

## Verification

Run the following commands to verify DNS propagation:

```
dig www.vaytrion.com +nostats +nocomments +nocmd
dig vaytrion.com +nostats +nocomments +nocmd
```

Expected results:
- `www.vaytrion.com` should resolve via CNAME to `joejojy.github.io`
- `vaytrion.com` should resolve to the four GitHub Pages IPs listed above

DNS propagation can take up to 48 hours.
