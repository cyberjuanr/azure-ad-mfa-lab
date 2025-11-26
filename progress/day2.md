# Day 2 Progress – Azure AD MFA + Azure VM Security Lab

## Objectives for Today
- Verify tenant-wide MFA enforcement using Security Defaults
- Review authentication methods and Conditional Access limitations
- Deploy an Azure Linux VM for security testing
- Configure Network Security Group (NSG) security
- Establish secure remote connectivity using SSH keys
- Validate Zero Trust access controls and cost management

---

## Tasks Completed

### 1. MFA Enforcement via Security Defaults
- Verified Microsoft Security Defaults are enabled tenant-wide.
- Confirmed that Security Defaults enforce MFA for all users automatically.
- Noted that Security Defaults block legacy authentication methods.

### 2. Authentication Method Review
- Checked Microsoft Authenticator configuration.
- Confirmed advanced MFA settings were unavailable due to licensing limits.
- Determined Conditional Access will be used later (requires P1 or P2).

### 3. Conditional Access Attempt
- Navigated to Microsoft Entra ID → Security → Conditional Access.
- Verified that the tenant cannot create custom Conditional Access policies without P1/P2 licensing.
- Confirmed that Security Defaults remain the active MFA enforcement mechanism.

### 4. Resource Group Setup
- Created AzureLabRG resource group.
- Assigned it to the Free Trial subscription.
- Selected Central US for consistency and availability.

---

## 5. Azure VM Deployment & Cost Control

### VM Deployment
- Resolved VM quota issues by selecting an available VM size in West US 2.
- Successfully deployed an Ubuntu 22.04 VM.
- Verified VM provisioning, OS type, and Azure guest agent status.
- Created NSG during setup.
- Confirmed assignment of public + private IP addresses.
- Confirmed VM reached “Running” state.

### Cost Awareness
- VM Cost: ~$0.096/hour while running.
- Charges only stop when VM is **Stopped (deallocated)**.
- Immediately deallocated VM after provisioning to protect credits.

---

## 6. Updated NSG (Network Security Group)
- Opened Network Settings → Network security group (AzureLabVM-NSG).
- Edited inbound SSH rule (Priority 1000).
- Changed **Source = My IP Address** instead of “Any.”
- Applied least-privilege access control.
- Verified all other inbound rules remained secure:
  - AllowVnetInBound
  - AllowAzureLoadBalancerInBound
  - DenyAllInBound

---

## 7. Configured SSH Key Authentication
- Downloaded `AzureLabKey.pem` during VM creation.
- Moved the key into the secure `.ssh` directory:
  ```bash
  mv AzureLabKey.pem ~/.ssh/
  chmod 400 ~/.ssh/AzureLabKey.pem
  ```
- Connected to VM securely with SSH:
  ```bash
  ssh -i ~/.ssh/AzureLabKey.pem azureadmin@<VM_PUBLIC_IP>
  ```

---

## 8. Validated Successful SSH Login
- Confirmed successful login with:
  - Ubuntu welcome banner
  - System load, uptime, update status
  - Private IP (172.16.x.x)
  - Logged-in username (`azureadmin`)
- Verified NSG rule correctly restricted SSH access to only my IP.

---

## Screenshots Added
- security-defaults-enabled.png
- auth-methods-page.png
- resource-group-created.png
- vm-deployment-success.png
- secure-ssh-connection.png

---

## Lessons Learned

### Identity & MFA
- Security Defaults provide strong MFA enforcement without P1/P2 licensing.
- Conditional Access cannot be configured without premium licensing.
- Authentication method options vary by licensing tier.

### VM & Networking
- Regional VM size availability varies due to quota limits.
- Alternative VM sizes can be used safely within free credits.
- NSGs enforce network segmentation and least privilege.
- SSH should always be restricted to a trusted IP.

### Cost Management
- VM billing continues while VM is running.
- Stopping the VM is not enough—must be **Stopped (deallocated)**.
- Always shut down lab VMs immediately when finished.

---

## Planned Next Steps
- Lab Completed ☑️

