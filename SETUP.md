# BrammerIS Website — Setup Guide

This folder contains the BrammerIS website: landing page, about page, and contact form.

## Files

- `index.html` — Landing page
- `about.html` — About Frank and BrammerIS
- `contact.html` — Contact form (name, email, message)
- `SETUP.md` — This file

## Deployment: GitHub Pages (Free)

### Step 1: Create GitHub Repository

1. Go to [github.com](https://github.com) and log in (create account if needed)
2. Create a new repository named `brammeris.com` (or any name)
3. Clone it to your local machine or upload files directly via GitHub web interface

### Step 2: Upload Files

Upload `index.html`, `about.html`, and `contact.html` to the repository root.

### Step 3: Enable GitHub Pages

1. Go to repository Settings → Pages
2. Under "Build and deployment," select:
   - Source: `Deploy from a branch`
   - Branch: `main` (or your default branch)
   - Folder: `/ (root)`
3. Click Save

Your site will be live at `https://[username].github.io/brammeris.com` or similar (GitHub will show you the URL).

## Domain Setup: Point brammeris.com to GitHub Pages

### Step 1: Get GitHub Pages IP Address

GitHub Pages uses these IP addresses (check current docs):
- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

### Step 2: Configure GoDaddy DNS

1. Log in to GoDaddy.com
2. Go to Domains → Find brammeris.com → DNS
3. Add an `A` record pointing to one of the GitHub IPs (use the first one)
4. Add a `CNAME` record:
   - Name: `www`
   - Value: `[your-github-username].github.io`

### Step 3: Configure GitHub Pages for Custom Domain

1. Go to your GitHub repository Settings → Pages
2. Under "Custom domain," enter `brammeris.com`
3. Click Save
4. GitHub will create a CNAME file automatically

### Step 4: Verify (can take 24–48 hours)

Test:
- `brammeris.com` should load your site
- `www.brammeris.com` should also work

If not working immediately, DNS propagation takes time. Check back in a few hours.

---

## Contact Form: Formspree Setup (Free)

The contact form needs a backend to email submissions. Formspree is free and handles this.

### Step 1: Create Formspree Account

1. Go to [formspree.io](https://formspree.io)
2. Sign up (free tier available)
3. Create a new form
4. Set email recipient to `contact@brammeris.com` (or your preferred email)
5. Formspree will give you a Form ID (looks like `f_abc123def456`)

### Step 2: Update contact.html

In `contact.html`, find this line (around line 160):

```javascript
fetch('https://formspree.io/f/YOUR_FORM_ID', {
```

Replace `YOUR_FORM_ID` with your actual Formspree ID from Step 1.

Example:
```javascript
fetch('https://formspree.io/f/f_abc123def456', {
```

### Step 3: Test

1. Upload updated `contact.html` to GitHub
2. Go to brammeris.com/contact.html
3. Fill out the form and submit
4. Formspree should email the submission to `contact@brammeris.com`

---

## Optional: Custom SMTP Email

If you want emails to come from a custom email (not Formspree's), you can configure SMTP in Formspree. Paid tier only, but worth it for a professional look.

---

## Future: Chatbot Integration

When ready to add a chatbot monitored by Agent, you can add a simple widget to the pages. Plan: build a lightweight chatbot that logs conversations to a file/database, which Agent monitors and responds to.

---

## Next Steps

1. Create GitHub repository and push files
2. Enable GitHub Pages
3. Set up Formspree
4. Update contact.html with Formspree ID
5. Configure GoDaddy DNS to point to GitHub Pages
6. Test brammeris.com and contact form

Once live, you can start sharing this URL when Agent reaches out to prospects.

---

## Notes

- Site is responsive (works on mobile, tablet, desktop)
- Uses modern, clean design with blue/gray + red accent colors
- No external dependencies (pure HTML/CSS/JS)
- Fast and secure (GitHub Pages = HTTPS by default)
- Cost: $0/month (GitHub Pages + Formspree free tier)
