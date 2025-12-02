# Deployment Guide

## Option 1: GitHub Actions (Recommended)

The repository includes a GitHub Actions workflow that automatically builds and deploys your site when you push to the `main` branch.

### Setup Steps

1. **Enable GitHub Pages in your repository:**
   - Go to repository Settings > Pages
   - Under "Build and deployment"
   - Set Source to: **GitHub Actions**

2. **Push your code:**
   ```bash
   git add .
   git commit -m "Add website content"
   git push origin main
   ```

3. **Monitor the deployment:**
   - Go to the "Actions" tab in your repository
   - Watch the "Deploy Hugo site to GitHub Pages" workflow
   - Once complete (green checkmark), your site is live

4. **Access your site:**
   - Visit https://evanspangler.github.io
   - It may take a few minutes for the first deployment

### Advantages
- Automatic deployment on every push
- No need to commit the `/public` folder
- Consistent build environment
- Easy to update (just push changes)

## Option 2: Manual Deployment

If you prefer to build locally and deploy manually:

### Setup Steps

1. **Build the site:**
   ```bash
   hugo
   ```

2. **Configure GitHub Pages:**
   - Go to repository Settings > Pages
   - Set Source to: **Deploy from a branch**
   - Select branch: `main`
   - Select folder: `/public` (or `/root` if you want to commit public to root)

3. **Commit and push:**
   ```bash
   git add public/
   git commit -m "Deploy website"
   git push origin main
   ```

4. **Note:** You'll need to remove `public/` from `.gitignore` if it's there

### Disadvantages
- Must remember to rebuild before pushing
- Larger repository size (includes built files)
- More manual steps

## Custom Domain (Optional)

If you want to use a custom domain like `evanspangler.com`:

1. **Add CNAME file:**
   ```bash
   echo "yourdomain.com" > static/CNAME
   ```

2. **Configure DNS with your domain registrar:**
   - Add A records pointing to GitHub Pages IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   - OR add CNAME record: `yourdomain.com` → `evanspangler.github.io`

3. **Update repository settings:**
   - Go to Settings > Pages
   - Enter your custom domain
   - Enable "Enforce HTTPS" (after DNS propagates)

4. **Update `config.toml`:**
   ```toml
   baseURL = "https://yourdomain.com"
   ```

## Troubleshooting

### Site not updating
- Check the Actions tab for build errors
- Ensure you pushed to the `main` branch
- Clear your browser cache

### 404 errors
- Verify `baseURL` in `config.toml` matches your actual URL
- Check that theme is properly installed (git submodule)
- Ensure Hugo build completed successfully

### Theme not loading
- Verify theme exists: `ls themes/hugo-theme-massively`
- If missing, run: `git submodule update --init --recursive`

### Images not displaying
- Ensure images are in `static/images/` directory
- Check file names match exactly (case-sensitive)
- Verify images are committed to git

## Making Updates

### Content Changes

1. Edit markdown files in `/content/` or data files in `/data/en/`
2. Test locally: `hugo server -D`
3. Commit and push:
   ```bash
   git add .
   git commit -m "Update content"
   git push origin main
   ```

### Configuration Changes

1. Edit `config.toml`
2. Test locally
3. Commit and push

The site will automatically rebuild and redeploy (if using GitHub Actions).

## Monitoring

### Check Site Status
- GitHub Actions: Repository > Actions tab
- GitHub Pages: Repository > Settings > Pages

### Analytics
If you added Google Analytics to `config.toml`, monitor traffic at:
https://analytics.google.com

## Security

### Protecting Contact Form
- Use a service like Formspree, Netlify Forms, or similar
- Never expose email processing scripts in the repository
- Consider adding CAPTCHA to prevent spam

### Repository Settings
- Keep repository public (required for free GitHub Pages)
- Never commit sensitive credentials or API keys
- Use environment secrets for any API integrations

## Support

- Hugo Documentation: https://gohugo.io/documentation/
- GitHub Pages: https://docs.github.com/en/pages
- Theme Documentation: Check themes/hugo-theme-massively/README.md
