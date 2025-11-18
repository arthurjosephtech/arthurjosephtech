Modern Device Onboarding & Pre-Provisioning Pipeline
End-to-End Automation of Windows Provisioning Using Intune, Okta, Autopilot, and Zero-Touch Deployment

This project documents the engineering of a modern, automated, and scalable onboarding pipeline for Windows devices at an enterprise law firm. The redesign replaces a slow and inconsistent process with a zero-touch, identity-driven provisioning workflow using:

Microsoft Intune (Win32 Pre-Provisioning + Autopilot ESP)

Okta (password-only first login; MFA enforced after enrollment)

Azure AD / Entra ID

Standardized security baselines and configuration automation

The result is a standardized, secure, sub-30-minute provisioning flow that significantly improves IT efficiency and the new-hire experience.

Executive Summary

Before this project, device onboarding:

Required 45–90 minutes

Involved manual setup

Frequently ran into MFA loops and inconsistent deployments

A new three-phase automated provisioning architecture was developed to:

Eliminate manual setup

Enforce consistent security configuration

Automate all app and policy deployment

Remove first-login MFA blockers

Reduce IT effort by ~70%

Deliver a fully configured desktop in under 30 minutes

This workflow is now the standard for all workstation deployments.

Architecture Overview

The onboarding pipeline consists of three stages:

+-------------------+        +----------------------+        +-----------------------+
| Phase 1           |        | Phase 2              |        | Phase 3               |
| Pre-Provisioning  | -----> | Okta Login           | -----> | Windows Autopilot     |
| (IT Prep Stage)   |        | Optimization         |        | Enrollment            |
+-------------------+        +----------------------+        +-----------------------+
     20–25 min                     Instant                        <10 min


Each stage ensures the device is fully prepared prior to the user’s first interaction.

Phase 1: Pre-Provisioning (20–25 Minutes)
Overview

This stage produces a ready-to-use, secure workstation before the end user signs in.

Applications Installed

Microsoft 365 Apps

Adobe Unifier

Cortex XDR

Uniflow Smart Client

GoToAssist (unattended access)

Cisco Jabber

SolarWinds Agent

Google Chrome

Okta Verify

These applications previously required 30–40 minutes of manual installation.

Policies Applied

Nine core security and configuration policies are deployed:

Microsoft LAPS

Windows EDR Baseline

Firewall allowed-apps configuration

Corporate desktop and lockscreen branding

Chrome Security Baseline

Taskbar layout standardization

25H2 Security Baseline

Security posture is established before the first user login.

Phase 2: Okta Login Optimization
Problem Identified

New hires were unable to authenticate because:

MFA must be set up during the first login

But MFA cannot be set up until after login

This created a circular dependency and frequent onboarding tickets.

Solution Implemented

A Conditional Access rule was implemented:

If device = Windows Autopilot:
    Allow password-only authentication
    Enforce MFA after MDM enrollment

Benefits

First login succeeds without a mobile device

IT receives fewer onboarding tickets

MFA compliance remains intact after enrollment

Phase 3: Windows Autopilot (<10 Minutes)
Overview

Autopilot completes the device's final configuration, including:

Applications Installed

Company Portal

Microsoft Teams

Additional Policies

Corporate Wi-Fi auto-connect profile

Chrome Security Baseline reinforcement

Skipped first-login animations

Streamlined ESP configuration

This phase consistently completes in under 10 minutes due to optimized ordering and dependency management.

Results and Impact
Provisioning Time Reduction

Old Workflow

45–90 minutes

Manual, inconsistent, error-prone

New Workflow

20–25 minutes (Pre-Provisioning)

Under 10 minutes (Autopilot)

~30 minutes total

Security Enhancements

Security baselines applied before the first login

LAPS on all devices

EDR active from first boot

Fully standardized build process

Operational Improvements

IT no longer logs into new devices

No MFA-related onboarding issues

Consistent and reliable app deployments

User Experience Improvements

Devices are functional immediately upon login

No waiting for applications or security policies

Reduced need for helpdesk support

Clean, professional, and secure initial desktop experience
