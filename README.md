Azure Entra ID Conditional Access Lab
Overview

This project simulates a real-world Conditional Access design scenario using Microsoft Entra ID.

The objective was to design and understand how organizations enforce secure access through Multi-Factor Authentication (MFA), location-based restrictions, privileged access controls, and risk-based policies following Zero Trust principles.

Objectives
Design Conditional Access policies for secure authentication
Enforce Multi-Factor Authentication (MFA)
Implement location-based access restrictions
Apply stricter controls to privileged accounts
Understand risk-based sign-in protection
Analyze limitations of the Free tier in Microsoft Entra ID
Environment
Microsoft Azure
Microsoft Entra ID (Free Tier)
Conditional Access (Design Only)
Policies Designed
1. Require MFA for All Users
Users: All users
Apps: All cloud apps
Conditions: Any location
Control: Require MFA
2. Block Access from Outside Portugal
Users: All users
Apps: All cloud apps
Conditions: Any location excluding Portugal
Control: Block access
3. Privileged Account Protection
Users: Directory roles (Admins)
Apps: All cloud apps
Conditions: Any location
Controls:
Require MFA
Require compliant device (if available)
4. Block High-Risk Sign-ins
Users: All users
Apps: All cloud apps
Conditions: High sign-in risk
Control: Block access
Expected Outcomes
Reduced risk of credential compromise through MFA
Restricted access from untrusted locations
Strong protection of administrative accounts
Prevention of suspicious or high-risk sign-ins
Key Learnings
Conditional Access policy design fundamentals
Zero Trust security principles in practice
Importance of MFA in identity protection
Role of location and risk signals in access control
Differences between Free and Premium Entra ID capabilities
Notes

This project was developed for learning and portfolio purposes.

Due to the use of the Microsoft Entra ID Free tier, Conditional Access policies could not be implemented, but the design reflects real-world enterprise configurations.
