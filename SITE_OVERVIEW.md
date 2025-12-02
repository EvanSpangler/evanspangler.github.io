# Evan Spangler Consulting Website

## Overview

Professional technology consulting website built with Hugo using the Massively theme. Comprehensive IT solutions from infrastructure and cloud to custom systems and security.

## Site Structure

### Main Pages

- **Home** (`/`) - Landing page with hero section and featured service cards
- **Services** (`/services`) - Comprehensive service offerings covering IT, custom systems, and security
- **CMMC Compliance** (`/cmmc-compliance`) - Detailed CMMC consulting services
- **About** (`/about`) - Company information and contact details

### Featured Service Cards (Homepage)

Six service highlight posts appear on the homepage:
1. Infrastructure & Cloud Solutions
2. Custom Electronics & Systems
3. Physical Security Systems
4. CMMC Compliance
5. Systems Integration
6. DevOps & Automation

## Content Positioning

### Target Audience
Organizations requiring technology solutions across infrastructure, custom systems, and security. No size restrictions - experience spans federal, startup, and enterprise environments.

### Key Differentiators
- Over a decade across federal, startup, and enterprise environments
- End-to-end capabilities from strategy to implementation
- Infrastructure expertise (Terraform, AWS, OCI, automation)
- Custom systems design (embedded systems, electronics, physical security)
- Real results (96% data distribution time reduction, military-grade systems, enterprise transformations)
- CMMC compliance experience (IonDesign Level 1, NIST 800-171 implementation)

### Tone
- Professional engineering focus
- Practical, results-oriented
- Business value emphasis
- Technical credibility without unnecessary complexity

## Service Areas

### IT Infrastructure & Cloud
- Infrastructure automation (Terraform, Ansible, Python)
- Cloud solutions (AWS, OCI, Azure)
- Virtualization (VMware, Proxmox, Xen)
- Network architecture
- Systems administration

### Custom Solutions
- Custom electronics and embedded systems
- Drive-thru car counters and traffic monitoring
- Physical security systems (access control, cameras, alarms)
- Industrial control systems
- Specialized hardware

### Security & Compliance
- CMMC Level 1 & 2
- NIST 800-171
- Security assessments
- Cross-domain solutions
- Incident response planning

### DevOps & Automation
- CI/CD pipelines
- Infrastructure-as-Code
- Configuration management
- Monitoring and logging
- Performance optimization

## Configuration Files

### `/config.toml`
Main Hugo configuration with site title, description, and post settings.

### `/data/en/`
YAML data files controlling site content:
- `intro.yaml` - Homepage hero section
- `contactinfo.yaml` - Contact information and form
- `nav.yaml` - Navigation menu items
- `social.yaml` - Social media links
- `post.yaml` - Post link text configuration

## Next Steps

### Before Going Live

1. **Update Contact Information**
   - Edit `/data/en/contactinfo.yaml` with your actual email
   - Configure form endpoint (currently uses Formspree placeholder)
   - Update social media links in `/data/en/social.yaml`

2. **Add Images**
   - Homepage hero background: `static/images/bg.jpg`
   - Service cards: `static/images/pic01.jpg` through `pic06.jpg`
   - Theme defaults will work until you add custom images

3. **Optional Customization**
   - Add Google Analytics ID in `config.toml` if desired
   - Customize theme colors (see theme documentation)
   - Add favicon: `static/favicon.ico`

4. **Legal Pages** (recommended)
   - Privacy policy
   - Terms of service

### Building & Deploying

```bash
# Local development server
hugo server -D

# Build for production
hugo

# Output will be in /public directory
```

### GitHub Pages Deployment

The site is configured for GitHub Pages at `https://evanspangler.github.io`

Ensure your repository settings:
- Source: `main` branch, `/public` folder OR use GitHub Actions
- Custom domain (optional): configure in repository settings

## Content Philosophy

All content is written for a business consulting context, not a personal resume:
- Focus on client benefits and business value
- Services described in terms of outcomes and capabilities
- Experience mentioned to establish credibility and demonstrate track record
- Professional engineering tone suitable for B2B consulting
- Technical credibility balanced with accessibility

## Editing Content

### Update Service Descriptions
Edit `/content/services.md`

### Update CMMC Information
Edit `/content/cmmc-compliance.md`

### Update Company Information
Edit `/content/about.md`

### Add/Edit Service Cards
Create/edit files in `/content/post/`

### Modify Homepage Text
Edit `/data/en/intro.yaml`

## Support

For Hugo-specific questions: https://gohugo.io/documentation/
For theme questions: https://github.com/curttimson/hugo-theme-massively
