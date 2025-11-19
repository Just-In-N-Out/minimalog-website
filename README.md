# MinimaLog Website

This directory contains the static website for minimalog.fit including OAuth redirects and privacy policy.

## Files Structure

```
website/
├── index.html              # Homepage
├── privacy.html            # Privacy Policy (required for App Store)
├── terms.html              # Terms of Service
└── auth/
    ├── callback.html       # OAuth callback redirect
    └── reset.html          # Password reset redirect
```

## Deployment Options

### Option 1: GitHub Pages (Recommended - FREE)

1. Create a new GitHub repository named `minimalog-website`
2. Upload all files from this `website/` folder to the repository
3. Go to repository Settings → Pages
4. Under "Source", select "Deploy from a branch"
5. Select "main" branch and "/ (root)" folder
6. Click Save
7. GitHub will give you a URL like `https://yourusername.github.io/minimalog-website`
8. Point your domain `minimalog.fit` to this URL using CNAME

**DNS Settings for GitHub Pages:**
- Add a CNAME record: `www.minimalog.fit` → `yourusername.github.io`
- Add A records for apex domain pointing to GitHub Pages IPs:
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153

### Option 2: Netlify (FREE)

1. Sign up at https://netlify.com
2. Drag and drop the `website/` folder to deploy
3. Configure custom domain in Netlify settings
4. Netlify will automatically configure SSL

### Option 3: Vercel (FREE)

1. Sign up at https://vercel.com
2. Import the `website/` folder as a new project
3. Configure custom domain in project settings
4. Vercel will automatically configure SSL

### Option 4: Cloudflare Pages (FREE)

1. Sign up at https://pages.cloudflare.com
2. Upload the `website/` folder
3. Configure custom domain
4. Cloudflare will handle DNS and SSL

## After Deployment

### Update Google OAuth Settings

1. Go to https://console.cloud.google.com/
2. Navigate to "APIs & Services" → "Credentials"
3. Edit your OAuth 2.0 Client ID
4. Add to "Authorized redirect URIs":
   ```
   https://minimalog.fit/auth/callback
   ```
5. Save changes

### Update OAuth Consent Screen

1. Go to "APIs & Services" → "OAuth consent screen"
2. Add "minimalog.fit" to "Authorized domains"
3. Save

## Important Notes

- Make sure all files are uploaded to the root of your domain
- The OAuth callback pages MUST be accessible at:
  - `https://minimalog.fit/auth/callback`
  - `https://minimalog.fit/auth/reset`
- Privacy policy MUST be accessible at:
  - `https://minimalog.fit/privacy.html`

## Testing

After deployment, test the URLs:
- https://minimalog.fit/ (should show homepage)
- https://minimalog.fit/privacy.html (should show privacy policy)
- https://minimalog.fit/terms.html (should show terms)
- https://minimalog.fit/auth/callback (should redirect)
- https://minimalog.fit/auth/reset (should redirect)

## Support

If you need help with deployment, contact:
- Email: support@minimalog.fit
