# AZ-104 Azure Administrator – Hands-on Project

## 1. Project Overview

This project demonstrates practical Azure administration skills through the creation and configuration of Azure resources using the Microsoft Azure Portal.

**Project Name:** AZ-104 Azure Administrator Practice Project

**Objective:** To gain hands-on experience with Azure resource management, virtual machines, networking, storage, security and access management.

## 2. Azure Resources

The project uses the following 7 Azure resources inside the Resource Group `rg-az104-practice`.

| Resource | Name | Region |
|---|---|---|
| Resource Group | rg-az104-practice | Resource group |
| Virtual Machine | vm-az104-practice | Central India |
| Virtual Network | vnet-centralindia-1 | Central India |
| Network Security Group | vm-az104-practice-nsg | Central India |
| Network Interface | vm-az104-practice242 | Central India |
| Public IP | vm-az104-practice-ip | Central India |
| OS Disk | vm-az104-practice_OsDisk_1_f718749e20474be7b9eba7478dd64814 | Central India |
| Storage Account | az104practice8912 | East US |

## 3. Virtual Machine and Networking Configuration

### Virtual Machine
- Name: vm-az104-practice
- Operating System: Windows
- Size: Standard B2als v2
- Region: Central India
- Availability Zone: Zone 1
- Status at project documentation: Stopped (deallocated)

### Virtual Network
- Name: vnet-centralindia-1
- Address Space: 172.16.0.0/16
- Subnet: snet-centralindia-1
- Subnet Address Range: 172.16.0.0/24

### Network Security Group (NSG)
- Name: vm-az104-practice-nsg
- Custom Inbound Rule: Allow-RDP-MyIP
- Priority: 100
- Protocol: TCP
- Port: 3389
- Source: 103.174.141.51/32
- Action: Allow

The Network Security Group is associated with the Virtual Machine's Network Interface.

## 4. Storage Configuration

### Storage Account
- Name: az104practice8912
- Account Type: StorageV2 (General-purpose v2)
- Performance: Standard
- Replication: Locally Redundant Storage (LRS)
- Access Tier: Hot

### Storage Security
- Secure Transfer Required: Enabled
- Minimum TLS Version: 1.2
- Anonymous Blob Access: Disabled
- HTTPS Only: Enabled

### Blob Storage Features
- Blob Soft Delete: Enabled (7 days)
- Blob Versioning: Enabled
- Blob Containers: Private access
- Lifecycle Management: Configured to move eligible base blobs under `az104-files/` to Cool tier after 30 days without modification.

### Shared Access Signature (SAS)
Practised generating an Account SAS with:
- Service: Blob
- Resource Type: Object
- Permission: Read
- Protocol: HTTPS only

The generated SAS had a limited validity period and is now expired.

## 5. Role-Based Access Control (RBAC)

RBAC was configured to practise role-based permissions using Microsoft Entra ID security groups.

### Security Group
- Group Name: AZ104-Practice-Group
- Group Type: Security
- Membership: Assigned

### Test User
- User: AZ104 Test User
- Added as a member of AZ104-Practice-Group.

### Role Assignments

| Role | Scope | Assignment |
|---|---|---|
| Contributor | Resource Group | Inherited through group |
| Reader | Resource Group | Inherited through group |
| Storage Blob Data Reader | Storage Account | Assigned to group |

Effective access was verified using **Access Control (IAM) → Check access**.

## 6. Architecture Diagram

The architecture diagram represents the Azure resources and their configuration across Central India and East US.

![Azure Architecture Diagram](Architecture%20Diagram.png)

## 7. Project Screenshots

Screenshots documenting the practical Azure configurations are available in the `Screenshots` folder.

1. Resource Group showing all 7 resources
2. Virtual Machine Overview
3. Network Security Group inbound rules
4. Virtual Network subnet
5. Storage Account Overview

## 8. Skills Practised

- Azure Resource Management
- Virtual Machine Configuration
- Virtual Network and Subnet Management
- Network Security Group Rules
- Azure Storage Account Management
- Blob Storage and Lifecycle Management
- Shared Access Signature
- Microsoft Entra ID Users and Groups
- Role-Based Access Control
- Azure Portal Administration

## 9. Learning Outcome

Through this project, I gained practical experience in deploying, configuring and managing Azure resources, applying access permissions, configuring storage security and understanding Azure networking concepts.

**Project Type:** Hands-on Learning and Practice Project  
**Platform:** Microsoft Azure  
**Tools:** Azure Portal, Microsoft Entra ID