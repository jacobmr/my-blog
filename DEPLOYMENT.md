# Deployment Guide

## Cloudflare Pages Setup

### Manual Steps (Recommended due to current internal error)

1. **Go to Cloudflare Dashboard**: https://dash.cloudflare.com/
2. **Navigate to Pages**: Select "Pages" from the left sidebar
3. **Create Application**: Click "Create application"
4. **Connect Git**: 
   - Click "Connect to Git"
   - Choose GitHub
   - Select `jacobmr/my-blog` repository
5. **Configure Build Settings**:
   ```
   Framework preset: Hugo
   Build command: hugo --minify
   Build output directory: public
   Root directory: / (leave empty)
   ```
6. **Environment Variables**:
   ```
   HUGO_VERSION = 0.148.2
   NODE_VERSION = 18 (optional)
   ```
7. **Deploy**: Click "Save and Deploy"

### Troubleshooting Cloudflare Pages Internal Error

If you encounter "an internal error occurred":

1. **Wait and Retry**: Internal errors are usually temporary
2. **Try Different Build Command**: Use `hugo` instead of `hugo --minify`
3. **Check Hugo Version**: Ensure HUGO_VERSION is set to 0.148.2 or latest
4. **Contact Support**: Use the link provided: https://cfl.re/3WgEyrH

### Alternative Build Commands

If the standard Hugo command fails, try:
```bash
# Basic build
hugo

# With minification
hugo --minify

# Production build with environment
HUGO_ENV=production hugo --minify
```

## Alternative: Netlify Deployment

If Cloudflare Pages continues having issues, you can deploy to Netlify:

1. **Go to Netlify**: https://netlify.com
2. **New Site from Git**: Connect your GitHub repository
3. **Build Settings**:
   ```
   Build command: hugo --minify
   Publish directory: public
   ```
4. **Environment Variables**:
   ```
   HUGO_VERSION = 0.148.2
   ```

## Alternative: Vercel Deployment

You can also deploy to Vercel:

1. **Go to Vercel**: https://vercel.com
2. **Import Project**: Connect your GitHub repository
3. **Framework**: Select "Hugo"
4. **Build Settings**: Usually auto-detected

## Local Development

```bash
# Start development server
hugo server --buildDrafts

# Or use npm script
npm run dev

# Build for production
hugo --minify
```

## Custom Domain Setup

Once deployed, you can add a custom domain in your hosting provider's dashboard:

1. **Cloudflare Pages**: Pages → Settings → Custom domains
2. **Netlify**: Site settings → Domain management
3. **Vercel**: Project settings → Domains

## Continuous Deployment

All platforms will automatically redeploy when you push to the `main` branch.

## Build Status

✅ Local build working
✅ Repository pushed to GitHub
⚠️  Cloudflare Pages deployment (internal error - retry recommended)