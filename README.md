🔐 Conditional Access Policy Design (Microsoft Entra ID)
📌 Overview

This project presents a security-focused Conditional Access design using Microsoft Entra ID, based on Zero Trust principles.

The objective is to demonstrate how organizations can protect cloud resources by enforcing strong authentication, controlling access conditions, and reducing identity-based risks.

⚠️ Note:
Due to licensing limitations (Free tier), these policies were not implemented but are fully designed following real-world enterprise practices.

🛡️ Policy 1 — Require MFA for All Users
🎯 Goal

Ensure all users perform Multi-Factor Authentication (MFA) when accessing cloud resources.

⚙️ Configuration
Users: All users
Cloud apps: All cloud applications
Conditions: Any location
Grant control: Require MFA
✅ Expected Outcome

All users must complete MFA before accessing resources, significantly reducing the risk of credential compromise.

🌍 Policy 2 — Block Access from Untrusted Locations
🎯 Goal

Restrict access to organizational resources from trusted geographic locations only.

⚙️ Configuration
Users: All users
Cloud apps: All cloud applications
Conditions:
Location: Any location excluding Portugal
Grant control: Block access
✅ Expected Outcome

Access attempts from outside Portugal are blocked, minimizing exposure to external threats.

⚠️ Note

Requires Microsoft Entra ID Premium (Conditional Access). Not available in the Free tier.

👑 Policy 3 — Enforce Strong Controls for Privileged Accounts
🎯 Goal

Apply enhanced security measures to administrative and high-privilege accounts.

⚙️ Configuration
Users: Directory roles (e.g., Global Administrator, User Administrator)
Cloud apps: All cloud applications
Conditions: Any location
Grant controls:
Require MFA
Require compliant device (if Intune is integrated)
✅ Expected Outcome

Privileged users must authenticate with MFA and, when applicable, use compliant devices, reducing the risk of privilege escalation or compromise.

⚠️ Note

Device compliance requires:

Microsoft Entra ID Premium
Microsoft Intune integration
🚨 Policy 4 — Block High-Risk Sign-ins
🎯 Goal

Prevent access when a sign-in is classified as high risk.

⚙️ Configuration
Users: All users
Cloud apps: All cloud applications
Conditions:
Sign-in risk level: High
Grant control: Block access
✅ Expected Outcome

High-risk sign-in attempts are automatically blocked, even if credentials are valid.

⚠️ Note

Requires Microsoft Entra ID Premium P2 for risk-based Conditional Access.

🧠 Key Security Concepts Applied

This design follows Zero Trust Architecture, enforcing:

🔐 Strong authentication (MFA)
🌍 Location-based access control
👑 Privileged identity protection
🚨 Risk-based access decisions
📊 Conclusion

This project demonstrates how to design a robust Identity and Access Management (IAM) strategy using Microsoft Entra ID.

Even without full implementation, it reflects real-world enterprise security practices, showing how organizations can:

Reduce identity-based attack surfaces
Protect privileged accounts
Enforce secure access policies
Align with Zero Trust principles
🚀 Final Note

Designing secure architectures is a critical skill in modern IT environments.
This project highlights the ability to plan, structure, and justify security controls, even when technical limitations are present.
