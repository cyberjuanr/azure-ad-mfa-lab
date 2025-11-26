# Day 2 Progress – Azure AD MFA Lab

## Objectives for Today
- Verify tenant-wide MFA enforcement using Security Defaults
- Create a Conditional Access policy to require MFA
- Begin secure VM deployment planning
- Prepare for Network Security Group (NSG) configuration

---

## Tasks Completed

### 1. MFA Enforcement via Security Defaults
- Verified that Microsoft Security Defaults are enabled at the tenant level.
- Confirmed that MFA is enforced for all users automatically.
- Security Defaults also block legacy authentication methods.

### 2. Authentication Method Review
- Reviewed Microsoft Authenticator authentication method settings.
- Confirmed that advanced MFA registration enforcement is restricted due to tenant licensing (no P1/P2).
- Validated that Conditional Access will be used for advanced access controls instead.

---

## Screenshots Added
- Security Defaults enabled page (tenant-wide MFA enforcement)
- Microsoft Authenticator settings page

---

## Lessons Learned
- Security Defaults provide baseline MFA and identity protection without additional licensing.
- Advanced MFA controls (such as forced registration) require Entra ID Premium licensing.
- Conditional Access is the correct control plane for enforcing MFA in Free Trial tenants.
- Identity security can be enforced at both the **authentication layer** and the **policy layer**.

---

## Planned Next Steps
- Create a Conditional Access policy requiring MFA for all users
- Deploy a secure Azure Virtual Machine using Free Tier resources
- Apply Network Security Group (NSG) rules to restrict inbound access
- Validate secure remote connectivity (RDP or SSH)

