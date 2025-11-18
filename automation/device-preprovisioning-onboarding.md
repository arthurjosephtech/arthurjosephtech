🚀 Modern Device Onboarding & Pre-Provisioning Pipeline
End-to-End Automation of Windows Provisioning Using Intune, Okta, Autopilot, and Zero-Touch Deployment

This project documents how I engineered a modern, automated, and scalable onboarding pipeline for Windows devices at an enterprise law firm.
The redesign replaces a slow, manual, and inconsistent process with a zero-touch, identity-driven provisioning workflow powered by:

Microsoft Intune (Win32 Pre-Provisioning + Autopilot ESP)

Okta (password-only first login + enforced MFA later)

Azure AD / Entra ID

Security baselines, app bundles, and policy automation

The result is a standardized, secure, and sub-30-minute provisioning flow that drastically improves IT efficiency and the new-hire experience.

🧩 Executive Summary

Before this project, device onboarding took 45–90 minutes, required hands-on IT involvement, and often failed due to MFA setup blockers, slow app deployments, or inconsistent configuration.

I designed and implemented a three-phase automated provisioning architecture that:

✔️ Eliminates manual setup
✔️ Enforces consistent security configuration
✔️ Automates all app + policy deployment
✔️ Bypasses first-login MFA blockers
✔️ Cuts IT effort by ~70%
✔️ Gets the user to a fully working desktop in under 30 minutes

This system now serves as the foundation for all future workstation deployments.

🏗️ Architecture Overview

The new pipeline consists of three tightly integrated phases:

+-------------------+        +---------------------+        +----------------------+
| Phase 1           |        | Phase 2             |        | Phase 3              |
| Pre-Provisioning  | -----> | Okta Login          | -----> | Windows Autopilot    |
| (IT prep stage)   |        | Optimization        |        | Enrollment           |
+-------------------+        +---------------------+        +----------------------+
       20–25 min                     Instant                        <10 min


Each phase handles specific components of the onboarding lifecycle, ensuring the device is fully ready before the user even begins logging in.

🔵 Phase 1 — Pre-Provisioning (20–25 Minutes)
Zero-Touch IT Prep Before the User Ever Sees the Device

The pre-provisioning stage creates a ready-to-go workstation, fully secured, fully patched, and preloaded with the firm’s core applications.

✅ Core Enterprise Applications Installed (Win32)

Win32 apps are packaged and silently deployed, including:

Microsoft 365 Apps

Adobe Unifier

Cortex XDR

Uniflow Smart Client

GoToAssist (unattended remote support)

Cisco Jabber

SolarWinds Agent

Google Chrome

Okta Verify

These applications used to take 30–40 minutes for IT to install manually.
Now they’re installed before the user ever logs in.

✅ Security & Configuration Policies Applied

Nine core policies are deployed during pre-provisioning, including:

Microsoft LAPS (local admin password rotation)

Windows EDR Baseline

Firewall allowed-apps configuration

KP25 Desktop Background & Lockscreen policy

Chrome security baseline

Taskbar layout standardization

25H2 Baseline Security Policy

This enforces full security posture before first login, not after.

🟣 Phase 2 — Okta Login Optimization
Password-Only First Login for a Smooth User Experience

One major bottleneck in the old system:
New users couldn’t log in without setting up MFA first, but they also couldn’t set up MFA until they logged in — a circular dependency that generated IT tickets daily.

🔧 Solution: Okta Conditional Access Policy

I implemented a logic rule:

If device = Windows Autopilot
→ Allow authentication with password only
→ Defer MFA enrollment until the device is fully enrolled

This accomplishes:

✔️ Fast first login
✔️ No cell phone needed during setup
✔️ Fewer help desk tickets
✔️ MFA still fully enforced once enrollment completes

This single adjustment removed one of the biggest friction points in user onboarding.

🟢 Phase 3 — Windows Autopilot (Under 10 Minutes)
Final User Personalization + Cloud Enrollment

Once the user logs in, Autopilot applies:

📦 Additional Applications

Company Portal

Microsoft Teams

🔐 Additional Policies

Corporate Wi-Fi auto-connect profile

Chrome security baseline reinforcement

Skipped first-login animations

Streamlined ESP tracking

With optimized ordering, application dependencies, and ESP settings, the entire Autopilot phase consistently completes in less than 10 minutes, even on fresh hardware.

🧠 Results & Impact
🚀 Provisioning Time Reduced by 60–75%

Old workflow:
45–90 minutes, highly manual
New workflow:
20–25 min pre-provisioning
<10 min Autopilot
≈ 30 minutes total

🔐 Stronger Security Posture

All baselines applied before first login

LAPS enforced on every device

EDR active from the first boot

Standardized application + config footprint

💼 Zero-Touch IT Operations

IT no longer needs to log into new devices

No more MFA enrollment blockers

No more inconsistent application deployment

😀 Better User Experience

New hires get a device that “just works”

No waiting for apps or policies to install

No first-day help desk calls

Clean, branded, secure desktop from minute one
