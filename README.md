# Secure Enterprise Network on Azure

## Overview
This project demonstrates the design and implementation of a **secure, segmented Azure virtual network** following **enterprise security and cost-optimization best practices**.

The goal was to deploy compute resources **without public exposure**, enforce **least-privilege network access**, and enable **secure administrative access**.

## Architecture
**Core components:**
- Azure Virtual Network with multiple subnets
- Network Security Groups (NSGs) per subnet
- Linux Virtual Machine without public IP
- Azure Bastion for secure access (temporary)

**Address Space**
- VNet: `10.0.0.0/16`
- Web Subnet: `10.0.1.0/24`
- App Subnet: `10.0.2.0/24`
- Management Subnet: `10.0.3.0/24`
- Azurebastation Subnet: '10.0.10.0/26'

## Security Design
- No public IP assigned to the VM
- Subnet-level NSGs enforcing least privilege
- Application subnet only allows traffic from Web subnet
- Management access via Azure Bastion only
- All unnecessary inbound traffic explicitly denied

This design reduces the attack surface and aligns with **Zero Trust principles**.

## Azure Services Used
- Azure Virtual Network
- Network Security Groups (NSGs)
- Azure Virtual Machines (B1s)
- Azure Bastion
- Azure Resource Groups

## Cost Management
- Used B1s VM (lowest-cost burstable SKU)
- Enabled auto-shutdown for compute resources
- Bastion deployed only for testing and removed immediately after
- All resources deployed in West Europe region

Estimated cost: **<$15**

## Validation & Testing
- SSH access from internet: Blocked
- SSH via Azure Bastion: Allowed
- Internet access to App subnet: Blocked
- Internal VNet traffic: Allowed

## Key Learnings
- Designing secure network boundaries in Azure
- Implementing least-privilege access using NSGs
- Secure VM access without public IPs
- Cost-aware cloud architecture decisions

## Future Improvements 
- Infrastructure as Code using Bicep
- Centralized logging with Azure Monitor
- Azure Policy enforcement for governance

## Author
Built by Olasehinde Victor 
