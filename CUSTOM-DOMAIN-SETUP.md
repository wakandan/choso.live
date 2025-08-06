# Custom Domain Setup Guide for GitHub Pages + Namecheap

This guide will walk you through setting up your GitHub Pages site with a custom domain purchased from Namecheap.

## 📋 Prerequisites

- ✅ GitHub repository with your static site
- ✅ Domain purchased from Namecheap
- ✅ Access to Namecheap DNS management
- ✅ GitHub Pages already enabled for your repository

## 🎯 Overview

You have two main options for your custom domain:
1. **Root domain** (e.g., `yourdomain.com`)
2. **Subdomain** (e.g., `www.yourdomain.com` or `blog.yourdomain.com`)

This guide covers both options.

---

## 🔧 Step 1: Configure DNS in Namecheap

### Option A: Root Domain Setup (yourdomain.com)

1. **Log into Namecheap**
   - Go to [Namecheap.com](https://www.namecheap.com)
   - Sign in to your account
   - Go to "Domain List" and click "Manage" next to your domain

2. **Access Advanced DNS Settings**
   - Click on the "Advanced DNS" tab
   - You'll see a list of DNS records

3. **Add A Records for GitHub Pages**
   Delete existing A records and add these four A records:
   ```
   Type: A Record
   Host: @
   Value: 185.199.108.153
   TTL: Automatic (or 1800)

   Type: A Record  
   Host: @
   Value: 185.199.109.153
   TTL: Automatic (or 1800)

   Type: A Record
   Host: @
   Value: 185.199.110.153
   TTL: Automatic (or 1800)

   Type: A Record
   Host: @
   Value: 185.199.111.153
   TTL: Automatic (or 1800)
   ```

4. **Add CNAME for www subdomain**
   ```
   Type: CNAME Record
   Host: www
   Value: your-username.github.io
   TTL: Automatic (or 1800)
   ```

### Option B: Subdomain Setup (www.yourdomain.com)

If you prefer to use a subdomain like `www.yourdomain.com`:

1. **Add CNAME Record**
   ```
   Type: CNAME Record
   Host: www
   Value: your-username.github.io
   TTL: Automatic (or 1800)
   ```

2. **Optional: Redirect root domain**
   ```
   Type: URL Redirect Record
   Host: @
   Value: https://www.yourdomain.com
   TTL: Automatic
   ```

---

## 🔧 Step 2: Update CNAME File

1. **Edit the CNAME file** in your repository root:
   ```
   # For root domain:
   yourdomain.com
   
   # For subdomain:
   www.yourdomain.com
   ```

2. **Commit and push** the CNAME file to your repository

---

## 🔧 Step 3: Configure GitHub Pages

1. **Go to your GitHub repository**
   - Navigate to your repository on GitHub
   - Click on "Settings" tab

2. **Access Pages Settings**
   - Scroll down to "Pages" in the left sidebar
   - Click on "Pages"

3. **Set Custom Domain**
   - In the "Custom domain" field, enter your domain:
     - `yourdomain.com` (for root domain)
     - `www.yourdomain.com` (for subdomain)
   - Click "Save"

4. **Enable HTTPS**
   - Check the "Enforce HTTPS" checkbox
   - ⚠️ Note: This might take 24-48 hours to become available

---

## 🔧 Step 4: Verification and Testing

### DNS Propagation Check
1. **Wait for DNS propagation** (can take up to 48 hours)
2. **Check DNS propagation** using online tools:
   - [DNS Checker](https://dnschecker.org/)
   - [What's My DNS](https://www.whatsmydns.net/)

### Test Your Domain
1. **Visit your domain** in a browser
2. **Check both versions**:
   - `http://yourdomain.com`
   - `https://yourdomain.com`
   - `http://www.yourdomain.com`
   - `https://www.yourdomain.com`

### Verify GitHub Pages Status
1. Go to your repository Settings → Pages
2. Look for a green checkmark and message: "Your site is published at https://yourdomain.com"

---

## 🛠️ Troubleshooting

### Common Issues and Solutions

#### 1. "Domain does not resolve" Error
- **Cause**: DNS records not properly configured or not propagated
- **Solution**: 
  - Double-check A records match GitHub's IP addresses
  - Wait up to 48 hours for propagation
  - Use DNS checking tools to verify

#### 2. "CNAME already in use" Error
- **Cause**: Another GitHub repository is using the same domain
- **Solution**: 
  - Remove the domain from the other repository
  - Or use a different subdomain

#### 3. SSL Certificate Issues
- **Cause**: HTTPS not available yet
- **Solution**:
  - Wait 24-48 hours after domain setup
  - Ensure "Enforce HTTPS" is checked in GitHub Pages settings
  - Try disabling and re-enabling HTTPS

#### 4. 404 Error on Custom Domain
- **Cause**: CNAME file missing or incorrect
- **Solution**:
  - Verify CNAME file exists in repository root
  - Check CNAME file contains only your domain (no protocol, no trailing slash)
  - Ensure CNAME file is committed and pushed

#### 5. Redirects Not Working
- **Cause**: Conflicting DNS records
- **Solution**:
  - Remove conflicting A or CNAME records
  - Ensure only necessary records exist

---

## 📊 DNS Records Summary

### For Root Domain (yourdomain.com):
| Type | Host | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 1800 |
| A | @ | 185.199.109.153 | 1800 |
| A | @ | 185.199.110.153 | 1800 |
| A | @ | 185.199.111.153 | 1800 |
| CNAME | www | your-username.github.io | 1800 |

### For Subdomain (www.yourdomain.com):
| Type | Host | Value | TTL |
|------|------|-------|-----|
| CNAME | www | your-username.github.io | 1800 |

---

## 🔐 Security Considerations

1. **Enable HTTPS**: Always use HTTPS for security
2. **HSTS Headers**: Consider adding security headers
3. **Regular Updates**: Keep your domain registration current
4. **Monitor**: Set up monitoring for your domain

---

## 📞 Support Resources

### Namecheap Support
- [Namecheap Knowledge Base](https://www.namecheap.com/support/knowledgebase/)
- Live chat support available 24/7

### GitHub Pages Documentation
- [GitHub Pages Custom Domain Guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [GitHub Community Forum](https://github.community/)

---

## ✅ Quick Checklist

Before going live, ensure:
- [ ] DNS A records point to GitHub's IP addresses
- [ ] CNAME file exists and contains correct domain
- [ ] GitHub Pages custom domain is configured
- [ ] DNS propagation is complete (24-48 hours)
- [ ] HTTPS is enabled and working
- [ ] All pages load correctly on custom domain
- [ ] Both www and non-www versions work (if desired)

---

## 🎉 Success!

Once everything is configured correctly, your GitHub Pages site will be accessible at your custom domain with:
- ✅ HTTPS encryption
- ✅ Fast global CDN delivery
- ✅ Professional custom domain
- ✅ Automatic deployments from GitHub

Your static website is now live on your custom domain! 🚀