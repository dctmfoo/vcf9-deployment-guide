# VCF 9 Deployment Guide

A comprehensive documentation site for VMware Cloud Foundation 9.0 deployment, migration, and Dell hardware compatibility.

**Live Site:** [vcf9-deployment-guide.pages.dev](https://vcf9-deployment-guide.pages.dev)

## Overview

This guide covers everything you need to deploy VCF 9.0 in existing VMware environments, including:

- **Migration Path**: VCF 4.5 → 5.2 → 9.0 (no direct upgrade from 4.5)
- **Architecture Changes**: New Fleet hierarchy, unified 9.x versioning
- **Component Changes**: SDDC Manager UI deprecated, VCF Operations now mandatory
- **Hardware**: Dell PowerEdge 16th/17th Gen server compatibility

## Documentation Sections

| Section | Description |
|---------|-------------|
| [Executive Summary](https://vcf9-deployment-guide.pages.dev/overview/summary/) | High-level overview and key changes |
| [Architecture](https://vcf9-deployment-guide.pages.dev/overview/architecture/) | Component versions (BOM) and Fleet hierarchy |
| [Requirements](https://vcf9-deployment-guide.pages.dev/requirements/vsphere/) | vSphere, vSAN, NSX, network prerequisites |
| [Deployment](https://vcf9-deployment-guide.pages.dev/deployment/cloud-builder/) | VCF Installer and Management Domain setup |
| [Integration](https://vcf9-deployment-guide.pages.dev/integration/identity/) | Identity, backup, lifecycle, RBAC |
| [Migration](https://vcf9-deployment-guide.pages.dev/migration/sddc-manager/) | SDDC Manager changes and gotchas |
| [Dell Hardware](https://vcf9-deployment-guide.pages.dev/hardware/dell-servers/) | PowerEdge servers, BIOS, firmware |

## Key Information

| Aspect | Details |
|--------|---------|
| VCF Version | 9.0.0.0 (Released June 17, 2025) |
| Upgrade Path | 4.5 → 5.2 → 9.0 |
| Key Change | SDDC Manager UI → VCF Operations |
| Mandatory Components | VCF Operations, VCF Automation |
| Dell Hardware | R760, R660, R670, R7625, R6615, R7725 |

## Tech Stack

- [Astro](https://astro.build) - Static site generator
- [Starlight](https://starlight.astro.build) - Documentation theme
- [Cloudflare Pages](https://pages.cloudflare.com) - Hosting

## Local Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Deployment

The site is deployed to Cloudflare Pages. To deploy manually:

```bash
npm run build
wrangler pages deploy dist --project-name vcf9-deployment-guide
```

## License

This documentation is provided for reference purposes.

## References

- [VCF 9.0 Release Notes](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-9-0-and-later/9-0/release-notes/vmware-cloud-foundation-90-release-notes.html)
- [VCF 9.0 Documentation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-9-0-and-later/9-0.html)
- [Broadcom Compatibility Guide](https://compatibilityguide.broadcom.com)
- [Dell vSAN Firmware Catalog](https://www.dell.com/support/kbdoc/en-us/000337386)
