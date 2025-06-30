# cloud-security-mini-lab
Hands on AWS lab that demonstrates secure network architecture,logging,detection and remediation of a misconfiguration.
---
## 🎯 Goal 
- Built a VPC with public & private subnets, jump-box and a private target EC2 then detect and remediate a too-permissive Secure shell protocol rule via CloudTrial.
---
  ## Skills 
  - VPC and subnet configuration  
  - Security Group management  
  - API-level logging with CloudTrail  
  - Incident detection and response 
---

## 🔍 Incident Simulation & Response

### 1. Inject Misconfiguration  
- **What:** Open SSH (TCP/22) to all IPv4 addresses on the private server’s security group.  
- **Why:** Simulates an accidental or malicious policy change.  

 

### 2. Detect via CloudTrail  
- **How:** In CloudTrail Event History, filter for `AuthorizeSecurityGroupIngress`.  
- **Outcome:** Identifies who and when port 22 was opened to the world.  

### 3. Remediate  
- **Action:** Remove the “open to all” SSH rule, restoring isolation.  

### 4. Confirm in CloudTrail  
- **Filter:** `RevokeSecurityGroupIngress`  
- **Outcome:** Verifies the insecure rule was removed.
