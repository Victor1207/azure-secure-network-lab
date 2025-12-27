# Network Design

This document explains the network layout used in this project.

## Virtual Network

- A single Virtual Network (`10.0.0.0/16`) was created to logically isolate resources.
- The address space allows room for future expansion.

## Subnet Design

- **Web Subnet (`10.0.1.0/24`)**
  - Intended for public-facing components.
- **Application Subnet (`10.0.2.0/24`)**
  - Hosts the Linux VM.
  - Accepts traffic only from trusted internal sources.
- **Management Subnet (`10.0.3.0/24`)**
  - Used only for administrative access via Azure Bastion.

## Result
Separating workloads into subnets improves security, clarity, and control.
