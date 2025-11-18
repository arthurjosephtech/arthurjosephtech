🚀 Modern Device Onboarding & Pre-Provisioning Pipeline
End-to-End Automation of Windows Provisioning Using Intune, Okta, Autopilot, and Zero-Touch Deployment

This project documents how I engineered a modern, automated, and scalable onboarding pipeline for Windows devices at an enterprise law firm.
The redesign replaces a slow, manual, inconsistent process with a zero-touch, identity-driven provisioning workflow built using:

Microsoft Intune (Win32 Pre-Provisioning + Autopilot ESP)

Okta (password-only first login → enforced MFA after enrollment)

Azure AD / Entra ID

Security baselines, app bundles, and automation policies

The result is a standardized, secure, sub-30-minute provisioning flow that drastically improves IT efficiency and the new-hire experience.

🧩 Executive Summary

Before this project, device onboarding:

Took 45–90 minutes

Required hands-on IT involvement

Frequently failed due to:

MFA setup blockers

Slow application deployments

Inconsistent policy application

I designed and implemented a three-phase automated provisioning architecture that:

✔️ Eliminates manual setup
✔️ Enforces consistent security configuration
✔️ Automates all application & policy deployment
✔️ Removes first-login MFA blockers
✔️ Cuts IT effort by ~70%
✔️ Gets users to a working desktop in under 30 minutes

This system is now the standard for all workstation deployments.

🏗️ Architecture Overview
Three-Phase Pipeline
+-------------------+        +----------------------+        +-----------------------+
| Phase 1           |        | Phase 2              |        | Phase 3               |
| Pre-Provisioning  | -----> | Okta Login           | -----> | Windows Autopilot     |
| (IT Prep Stage)   |        | Optimization         |        | Enrollment            |
+-------------------+        +----------------------+        +-----------------------+
       20–25 min                    Instant                        <10 min


Each phase handles a specific part of the lifecycle, ensuring a fully configured workstation before first login.

🔵 Phase 1 — Pre-Provisioning (20–25 Minutes)
Zero-touch IT prep before the user ever sees the device

This phase produces a ready-to-use, secure, and fully configured workstation, including:

✅ Core Applications Installed (Win32)

Microsoft 365 Apps

Adobe Unifier

Cortex XDR

Uniflow Smart Client

GoToAssist (unattended remote support)

Cisco Jabber

SolarWinds Agent

Google Chrome

Okta Verify

Previously, these took 30–40 minutes to install manually.
Now they’re done automatically.

✅ Security & Configuration Policies Applied

Nine core policies are deployed, including:

Microsoft LAPS (local admin password rotation)

Windows EDR Baseline

Firewall – Allowed Apps

Corporate Background + Lockscreen

Chrome Security Baseline

Taskbar Layout Standardization

25H2 Security Baseline

➡️ Security posture is enforced before the user ever logs in.

🟣 Phase 2 — Okta Login Optimization
Password-only authentication for the first login

Previously, users were stuck in a loop:

They couldn’t log in without MFA →
They couldn’t enroll MFA without logging in.

This created daily onboarding tickets.

🔧 Solution: Okta Conditional Access Logic
IF device = Windows Autopilot
THEN allow password-only login
THEN require MFA after enrollment

Benefits

✔️ Fast first login
✔️ No phone needed during setup
✔️ Eliminates MFA blocker tickets
✔️ MFA still enforced after MDM enrollment

🟢 Phase 3 — Windows Autopilot (<10 Minutes)
Final user personalization + cloud enrollment

Autopilot applies:

📦 Additional Applications

Microsoft Teams

Company Portal

🔐 Additional Policies

Wi-Fi auto-configure profile

Chrome Baseline Reinforcement

Skip first-login animations

Streamlined ESP tracking

Optimized deployment ensures this phase consistently completes in under 10 minutes.

🧠 Results & Impact
🚀 Provisioning Time Reduced by 60–75%
Old workflow

⏳ 45–90 minutes
🛠 Manual setup
🐛 Frequent failures

New workflow

⏱ 20–25 min pre-provisioning
⏱ <10 min Autopilot
➡️ ≈ 30 minutes total

🔐 Stronger Security Posture

Policies applied before user login

LAPS enforced on all devices

EDR active from first boot

Standardized configuration across all hardware

💼 Zero-Touch IT Operations

IT never logs into new machines

No MFA enrollment issues

No inconsistent application deployments

Hands-free baseline enforcement

😀 Better User Experience

Laptop “just works” on first boot

No delays waiting for apps to install

Zero first-day helpdesk calls

Clean, branded, secure desktop

✔️ This Markdown Is GitHub-Optimized

Uses proper # headings

Lists render properly

ASCII diagram renders correctly

Emoji spacing fixed

All sections visually structured

Works perfectly in light/dark mode
