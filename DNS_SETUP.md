# DNS Configuration Guide for memaphotos.com

## Issue with Namecheap API

The Namecheap API returned an error:
```
Error Number: 1011102
API Key is invalid or API access has not been enabled
```

This means either:
1. The API key needs to be regenerated
2. API access needs to be enabled in your Namecheap account settings
3. Your IP address needs to be whitelisted for API access

## Manual DNS Configuration (Recommended)

Since the API isn't working, here's how to configure DNS manually in Namecheap:

### Step 1: Log into Namecheap

1. Go to https://www.namecheap.com
2. Log in to your account
3. Go to "Domain List"
4. Click "Manage" next to memaphotos.com

### Step 2: Configure DNS Records

1. Go to the "Advanced DNS" tab
2. Delete any existing A records and CNAME records for @ and www
3. Add the following records:

#### A Records (for apex domain)

| Type | Host | Value | TTL |
|------|------|-------|-----|
| A Record | @ | 185.199.108.153 | Automatic |
| A Record | @ | 185.199.109.153 | Automatic |
| A Record | @ | 185.199.110.153 | Automatic |
| A Record | @ | 185.199.111.153 | Automatic |

#### CNAME Record (for www subdomain)

| Type | Host | Value | TTL |
|------|------|-------|-----|
| CNAME Record | www | artomatica.github.io. | Automatic |

**Important**: Make sure the CNAME value ends with a period (.)

### Step 3: Save Changes

1. Click "Save All Changes"
2. Wait for DNS propagation (can take 5 minutes to 48 hours, usually ~30 minutes)

### Step 4: Enable GitHub Pages

1. Go to https://github.com/Artomatica/memaphotos.com
2. Click "Settings" → "Pages"
3. Under "Source", select "main" branch
4. Under "Custom domain", enter: `memaphotos.com`
5. Wait for DNS check to complete (GitHub will verify the DNS records)
6. Once verified, check "Enforce HTTPS"

### Step 5: Verify

After DNS propagates, verify the setup:

```bash
# Check DNS resolution
dig memaphotos.com
dig www.memaphotos.com

# Should show GitHub Pages IPs for apex domain
# Should show artomatica.github.io for www subdomain
```

Visit https://memaphotos.com to confirm the site is live.

## Alternative: Enable Namecheap API Access

If you want to use the API in the future:

1. Log into Namecheap
2. Go to Profile → Tools → API Access
3. Enable API access
4. Whitelist your IP address
5. Generate a new API key if needed

## Current Status

- ✅ Website files created and pushed to GitHub
- ✅ CNAME file added to repository
- ⏳ DNS configuration pending (manual setup required)
- ⏳ GitHub Pages setup pending (after DNS)

Once DNS is configured, the site will be live at https://memaphotos.com within 30 minutes to 48 hours.
