# Security Decisions

This document explains the security choices made in this project.

## Key Decisions

- The Linux VM was deployed without a public IP to prevent direct internet access.
- Network Security Groups (NSGs) are applied at the subnet level.
- Only required inbound traffic is allowed; all other traffic is denied.
- Azure Bastion is used for secure administrative access instead of SSH over the internet.
- Management access is isolated in a separate subnet.

## Result
This design reduces the attack surface and follows least-privilege principles.
