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
  
### 3. Conditional Access Attempt
- Navigated to Microsoft Entra ID > Security > Conditional Access.
- Confirmed that custom Conditional Access policy creation is restricted due to lack of Entra ID Premium (P1/P2) licensing.
- Validated that Security Defaults are the active enforcement mechanism for tenant-wide MFA.

### 4. Resource Group Setup
- Created a dedicated resource group named AzureLabRG.
- Assigned it to the Free Trial subscription.
- Selected Central US as the region for lab consistency and availability.

---

## Screenshots Added
- Security Defaults enabled page (tenant-wide MFA enforcement)
- Microsoft Authenticator settings page
- Resource Group Creation Confirmation

---

## Lessons Learned
- Security Defaults provide baseline MFA and identity protection without additional licensing.
- Advanced MFA controls (such as forced registration) require Entra ID Premium licensing.
- Conditional Access policy creation requires Entra ID Premium P1 or P2.
- Free Trial tenants rely on Security Defaults for baseline Zero Trust enforcement.
- Licensing directly impacts available cloud security control planes.


---

## Planned Next Steps
- Deploy a secure Azure Virtual Machine using Free Tier resources
- Apply Network Security Group (NSG) rules to restrict inbound access
- Validate secure remote connectivity (RDP or SSH)

