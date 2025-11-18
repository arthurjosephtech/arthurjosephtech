# 🚀 **Modern Device Onboarding & Pre-Provisioning Pipeline**
### _End-to-End Automation Using Intune, Okta, Autopilot, and Zero-Touch Deployment_

This project outlines a fully automated, scalable onboarding pipeline for Windows devices at an enterprise law firm.  
The new workflow replaces a slow, inconsistent, and labor-heavy process with a **zero-touch, identity-driven provisioning system** powered by:

- **Microsoft Intune** (Win32 Pre-Provisioning + Autopilot ESP)  
- **Okta** (password-only first login → MFA enforced post-enrollment)  
- **Azure AD / Entra ID**  
- **Security baselines & configuration automation**

The result is a **secure, standardized, sub-30-minute provisioning flow** that dramatically improves IT efficiency and the end-user experience.

---

# 🧩 **Executive Summary**

Before this project, device onboarding:

- Required **45–90 minutes**  
- Needed hands-on IT interaction  
- Frequently failed due to MFA login loops  
- Had slow and inconsistent app deployment  
- Left devices unsecured until after login  

I engineered a **three-phase architecture** that:

- **Eliminates manual setup**  
- **Applies security baselines before login**  
- **Automates all app + policy deployments**  
- **Removes first-login MFA blockers**  
- **Reduces IT effort by ~70%**  
- **Delivers a ready-to-use desktop in under 30 minutes**  

This is now the enterprise-standard workflow.

---

# 🏗️ **Architecture Overview**

The onboarding lifecycle runs through three stages:

+-------------------+ +----------------------+ +-----------------------+
| Phase 1 | | Phase 2 | | Phase 3 |
| Pre-Provisioning | -----> | Okta Login | -----> | Windows Autopilot |
| (IT Prep Stage) | | Optimization | | Enrollment |
+-------------------+ +----------------------+ +-----------------------+
20–25 min Instant <10 min

yaml
Copy code

---

# 🔵 **Phase 1 — Pre-Provisioning (20–25 Minutes)**  
### _Zero-touch IT preparation before the employee receives the device_

This step produces a workstation that is **patched, secured, and fully configured** before the user signs in.

---

## **✔ Core Enterprise Applications Installed (Win32)**

- **Microsoft 365 Apps**  
- **Adobe Unifier**  
- **Cortex XDR**  
- **Uniflow Smart Client**  
- **GoToAssist**  
- **Cisco Jabber**  
- **SolarWinds Agent**  
- **Google Chrome**  
- **Okta Verify**  

These applications previously required **30–40 minutes** of manual work.

---

## **✔ Security & Configuration Policies Applied**

Nine major baseline and configuration policies, including:

- **Microsoft LAPS**  
- **Windows EDR Baseline**  
- **Firewall allowed-apps configuration**  
- **Corporate lockscreen + desktop branding**  
- **Chrome Security Baseline**  
- **Taskbar layout standardization**  
- **25H2 Security Baseline**  

➡️ _Security posture is enforced **before** user login — not after._

---

# 🟣 **Phase 2 — Okta Login Optimization**

Previously, new hires were blocked by a circular MFA requirement:

- They **couldn’t log in without MFA**  
- They **couldn’t set up MFA until after login**  

This created many onboarding tickets.

---

### **🔧 Conditional Access Logic Implemented**

If device = Windows Autopilot:
Allow password-only login
Enforce MFA after enrollment

yaml
Copy code

### **Benefits**

- ✔ **Fast, frictionless first login**  
- ✔ **Phone not required during setup**  
- ✔ **Dramatic reduction in MFA-related tickets**  
- ✔ **MFA still enforced after enrollment completes**

---

# 🟢 **Phase 3 — Windows Autopilot (<10 Minutes)**  
### _Final user personalization and cloud enrollment_

Autopilot completes the final steps:

---

## ✔ **Additional Applications Installed**

- **Microsoft Teams**  
- **Company Portal**

---

## ✔ **Additional Policies Enforced**

- **Corporate Wi-Fi auto-connect profile**  
- **Chrome baseline reinforcement**  
- **Skip first-login animations**  
- **Streamlined ESP configuration**  

Optimized ordering ensures this stage finishes in **less than 10 minutes**.

---

# 🧠 **Results & Impact**

## 🚀 **Provisioning Time Reduced by 60–75%**

**Old Workflow:**  
- 45–90 minutes  
- Manual  
- Error-prone  

**New Workflow:**  
- 20–25 min (Pre-Provisioning)  
- <10 min (Autopilot)  
- **≈ 30 minutes total**

---

## 🔐 **Significantly Stronger Security Posture**

- Baselines applied pre-login  
- LAPS enabled everywhere  
- EDR active from the first boot  
- Fully standardized workstation builds  

---

## 💼 **Zero-Touch IT Operations**

- IT never logs into new machines  
- No MFA login blockers  
- No inconsistent app deployments  
- Minimal administrative overhead  

---

## 😀 **Better User Experience**

- Device “just works” immediately  
- No app installation delays  
- No day-one helpdesk tickets  
- Clean, professional workspace on first login  

---
