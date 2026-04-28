# Azure Entra Conditional Access Design Lab

## Overview
This project demonstrates the design of Conditional Access policies using Microsoft Entra ID, based on a Zero Trust security model.

Due to Microsoft Entra ID Free tier limitations, Conditional Access policies could not be implemented directly. Instead, this project focuses on designing real-world security controls based on enterprise best practices.

---

## Scenario
This project simulates a small organization that needs to secure access to its cloud resources.

The organization aims to:
- Ensure only legitimate users can access systems
- Enforce Multi-Factor Authentication (MFA)
- Restrict access based on location
- Protect against risky sign-ins
- Allow access only from compliant devices

### Actors
- **Admin User** – manages the environment and security configurations  
- **Standard User (João Silva)** – represents a typical employee  

### Resources
- Microsoft Entra ID tenant  
- Cloud applications  
- My Apps portal  

---

## Conditional Access Limitation

Microsoft Entra ID Free tier does not support Conditional Access policies.

As a result:
- Policies cannot be created or enforced
- Advanced security features are restricted

This project adapts to this limitation by focusing on **security design and architecture**, which reflects real-world planning in enterprise environments.

---

## Conditional Access Policy Design

### Policy 1 — Require MFA for all users

**Goal:**  
Ensure all users must perform Multi-Factor Authentication when accessing cloud resources.

**Configuration (Design):**
- Users: All users
- Cloud apps: All cloud apps
- Conditions: Any location
- Grant control: Require MFA

**Expected Outcome:**  
All users must complete MFA before gaining access, reducing the risk of compromised credentials.

---

### Policy 2 — Block access from outside allowed locations

**Goal:**  
Restrict access to company resources only from trusted geographic locations.

**Configuration (Design):**
- Users: All users
- Cloud apps: All cloud apps
- Conditions:
  - Location: Any location EXCEPT Portugal
- Grant control: Block access

**Expected Outcome:**  
Any login attempt from outside Portugal will be blocked, reducing exposure to external threats.

**Note:**  
This policy requires Microsoft Entra ID Premium (Conditional Access).

---

### Policy 3 — Enforce stricter controls for administrators

**Goal:**  
Apply stronger security controls to privileged accounts.

**Configuration (Design):**
- Users: Directory roles (e.g., Global Administrator)
- Cloud apps: All cloud apps
- Conditions: Any location
- Grant controls:
  - Require MFA
  - Require compliant device (if using Intune)

**Expected Outcome:**  
Administrative users must use MFA and secure devices, reducing the risk of privilege compromise.

**Note:**  
Device compliance requires Microsoft Entra ID Premium and Microsoft Intune.

---

### Policy 4 — Block high-risk sign-ins

**Goal:**  
Prevent access when a sign-in is detected as high risk.

**Configuration (Design):**
- Users: All users
- Cloud apps: All cloud apps
- Conditions:
  - Sign-in risk: High
- Grant control: Block access

**Expected Outcome:**  
High-risk login attempts are automatically blocked, preventing unauthorized access.

**Note:**  
Sign-in risk evaluation requires Microsoft Entra ID Premium P2.

---

## Key Learnings

- Understanding of Conditional Access and Zero Trust principles  
- Ability to design security policies based on real-world scenarios  
- Awareness of Microsoft Entra ID licensing limitations  
- Practical approach to adapting security architecture when full implementation is not possible  

---

## Screenshots

### Conditional Access Overview
[See Screenshot](https://github.com/xoxpto/azure-entra-conditional-access-lab/blob/main/screenshots/01-conditional-access-overview.png)

### License Limitation
[See Screenshot](https://github.com/xoxpto/azure-entra-conditional-access-lab/blob/main/screenshots/02-conditional-access-license-limitation.png)

---

## Conclusion

This project demonstrates a security-first approach to Identity and Access Management using Microsoft Entra ID.

Although Conditional Access policies could not be implemented due to licensing limitations, the design reflects real-world enterprise security practices based on Zero Trust principles.

The project highlights the importance of:
- Strong authentication (MFA)
- Location-based access control
- Privileged account protection
- Risk-based access decisions
