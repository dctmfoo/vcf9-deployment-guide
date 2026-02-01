---
title: Executive Summary
description: High-level overview of VCF 9.0 deployment and migration paths
---

This guide provides comprehensive information for deploying VMware Cloud Foundation 9.0 within existing VMware environments. VCF 9.0, released June 17, 2025, introduces significant architectural changes including unified versioning (all components at 9.x), a new Fleet management hierarchy, and mandatory deployment of VCF Operations and VCF Automation.

## What's New in VCF 9.0

VCF 9.0 represents a major evolution of the platform with consolidated component versioning and a unified operations experience:

| Aspect | Details |
|--------|---------|
| **Release Date** | June 17, 2025 |
| **Unified Versioning** | All components now at 9.x (vSphere, NSX, vSAN, SDDC Manager) |
| **New Architecture** | Three-layer hierarchy: Private Cloud → Fleet → Instance |
| **Operations Console** | VCF Operations replaces SDDC Manager UI for day-2 operations |
| **Mandatory Components** | VCF Operations and VCF Automation now required |

## Critical Migration Notes

:::caution[No Direct Upgrade from 4.5]
Direct upgrade from VCF 4.5 to 9.0 is **NOT** supported. Required path: **VCF 4.5 → VCF 5.2 → VCF 9.0**
:::

### Key Changes from Previous Versions

| Change | Impact |
|--------|--------|
| SDDC Manager UI | Deprecated (use VCF Operations console) |
| VCF Operations & Automation | Now **mandatory** components |
| Cloud Builder | Replaced by VCF Installer appliance |
| Excel Deployment Workbook | Replaced by JSON specification or UI wizard |
| Identity Management | vIDM replaced by VCF Identity Broker |
| Licensing | Single license file, subscription-based only |

## Deployment Overview

A typical VCF 9 deployment involves the following phases:

### 1. Assessment & Planning
- Review existing vSphere, vSAN, and NSX infrastructure for VCF 9 readiness
- Validate hardware compatibility against [Dell PowerEdge requirements](/hardware/dell-servers/) or VMware HCL
- Verify [network prerequisites](/requirements/network/) and [DNS/NTP configuration](/requirements/dns-ntp-certs/)
- Confirm [licensing requirements](/requirements/licensing/)

### 2. Environment Preparation
- Prepare ESXi hosts (firmware, BIOS settings, networking, vSAN configuration)
- Configure prerequisite VLANs and IP schemas
- Deploy and validate VCF 9 imaging/bring-up bundles

### 3. Management Domain Deployment
- Deploy the [VCF 9 Management Domain](/deployment/management-domain/) using VCF Installer
- Configure vCenter Server, SDDC Manager, and vSAN
- Perform post-deployment validation

### 4. Integration & Configuration
- Configure [identity integration](/integration/identity/) with enterprise IdP
- Set up [backup solutions](/integration/backup/)
- Configure [lifecycle management](/integration/lifecycle/)
- Implement [RBAC and security best practices](/integration/rbac-security/)

### 5. Workload Domain Expansion
- Plan and deploy [Workload Domains](/deployment/workload-domains/) as needed
- Configure domain-specific networking and storage

## Quick Links

- [Architecture Overview](/overview/architecture/) - Component versions and BOM
- [Version Evolution](/overview/version-evolution/) - Changes from 4.5 → 5.2 → 9.0
- [Migration Gotchas](/migration/gotchas/) - Known issues and workarounds
- [SDDC Manager Changes](/migration/sddc-manager/) - Feature migration map

---

*Last Updated: February 2026*
