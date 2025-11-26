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

### 5. Azure VM Deployment & Cost Control 
## Tasks Completed
- Resolved VM quota limitation by selecting available VM size
- Deployed Ubuntu Linux virtual machine successfully
- Verified VM provisioning and agent status
- Configured Network Security Group during deployment
- Assigned public and private IP addresses to VM
- Verified VM was running and reachable
- Stopped (deallocated) VM to prevent unnecessary charges

## VM Configuration Details
- VM Name: AzureLabVM
- OS: Ubuntu Server 22.04 LTS
- VM Size: Standard_D2as_v4 (2 vCPU, 8 GiB RAM)
- Resource Group: AzureLabRG
- Region: West US 2
- Disk Type: Standard SSD
- Networking: Public + Private IP assigned
- NSG: AzureLabVM-NSG

## Cost & Billing Awareness
- VM cost while running: ~$0.096/hour
- Confirmed that charges stop only when VM is in:
  "Stopped (deallocated)" state
- Verified Azure credits will be used instead of personal billing
- Learned to stop VM immediately when not in use
---

## Screenshots Added
- Security Defaults enabled page (tenant-wide MFA enforcement)
- Microsoft Authenticator settings page
- Resource Group Creation Confirmation
- vm-deployment-success.png


---

## Lessons Learned
- Security Defaults provide baseline MFA and identity protection without additional licensing.
- Advanced MFA controls (such as forced registration) require Entra ID Premium licensing.
- Conditional Access policy creation requires Entra ID Premium P1 or P2.
- Free Trial tenants rely on Security Defaults for baseline Zero Trust enforcement.
- Licensing directly impacts available cloud security control planes.
- Free-tier VM sizes may be unavailable due to regional quota limits
- Alternative VM sizes can be used safely with credits
- VM costs accrue as long as the VM is running
- Stopping is not enough — VM must be "deallocated"
- NSGs control traffic at the network level


---

## Planned Next Steps
- Apply Network Security Group (NSG) rules to restrict inbound access
- Validate secure remote connectivity (RDP or SSH)

