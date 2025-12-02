# Pre-Launch Checklist

## Required Changes

### 1. Contact Information
**File:** `data/en/contactinfo.yaml`

- [ ] Replace `contact@evanspangler.com` with your actual email
- [ ] Update contact form action URL (sign up at https://formspree.io or use alternative)
- [ ] Optionally add phone number if you want to be contacted by phone
- [ ] Consider whether to specify a service area/location

### 2. Social Media Links
**File:** `data/en/social.yaml`

- [ ] Add your LinkedIn profile URL (replace the `#` placeholder)
- [ ] Add any other professional social profiles (GitHub, Twitter, etc.)
- [ ] Remove social section if you prefer not to include social links

### 3. Images
**Directory:** `static/images/`

The theme expects these images:
- [ ] `bg.jpg` - Homepage hero background image (deleted file exists in git status)
- [ ] `pic01.jpg` through `pic06.jpg` - Service card images on homepage

**Options:**
- Add your own professional images
- Use stock photos from sites like Unsplash
- Leave blank and theme will use defaults

**Recommended sizes:**
- Background: 1920x1080px or similar widescreen
- Service cards: 800x600px or similar 4:3 ratio

### 4. Review Content for Accuracy

- [ ] Review `/content/services.md` - ensure all services listed are offered
- [ ] Review `/content/cmmc-compliance.md` - verify CMMC details match your approach
- [ ] Review `/content/about.md` - personalize as needed
- [ ] Check all service card posts in `/content/post/` directory

### 5. Optional Enhancements

- [ ] Add Google Analytics tracking ID in `config.toml` (if desired)
- [ ] Create privacy policy page at `/content/privacy.md`
- [ ] Create terms of service at `/content/terms.md`
- [ ] Add favicon: create `static/favicon.ico`
- [ ] Consider adding client testimonials or case studies (if you have permission)

## Testing Before Launch

### Local Testing
```bash
# Start development server
hugo server -D

# Open browser to http://localhost:1313
# Check all pages load correctly
# Test navigation between pages
# Verify contact information displays correctly
```

### Check List
- [ ] All navigation links work
- [ ] Contact form submits correctly (if configured)
- [ ] All content displays properly on mobile devices
- [ ] No placeholder text remains (search for "example", "placeholder", "TODO")
- [ ] Email links work correctly
- [ ] Social media links go to correct profiles

## Deployment

### GitHub Pages Setup

1. **Build the site:**
   ```bash
   hugo
   ```

2. **Commit and push:**
   ```bash
   git add .
   git commit -m "Initial website content"
   git push origin main
   ```

3. **Configure GitHub Pages:**
   - Go to repository Settings > Pages
   - Set source to `main` branch, `/public` folder
   - OR use GitHub Actions for automated deployment

4. **Verify deployment:**
   - Visit https://evanspangler.github.io
   - Check that all pages load correctly

### Post-Launch

- [ ] Submit site to Google Search Console
- [ ] Test contact form by sending yourself a test message
- [ ] Monitor for any broken links or errors
- [ ] Consider setting up analytics to track visitor behavior

## Content Updates

To update content after launch, edit the markdown files and rebuild:

```bash
# Edit content files as needed
hugo

# Commit and push changes
git add .
git commit -m "Update content"
git push origin main
```

Changes should appear on the live site within a few minutes.
