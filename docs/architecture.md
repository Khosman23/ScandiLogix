# Architecture – ScandiLogix

This document describes the architecture of the ScandiLogix Power Platform solution and how its components work together to support secure, scalable logistics workflows.

---

## High-Level Architecture

ScandiLogix is built using the standard Power Platform pattern:

**Power Apps (UI)** → **Dataverse (Data + Security)** → **Power Automate (Automation)** → **Microsoft 365 (Notifications)**

The diagram below shows the main components and data flow:

```mermaid
flowchart LR
  subgraph Users
    A[Admin]
    D[Dispatcher]
    R[Driver]
    C[Customer]
  end

  subgraph PowerPlatform[Microsoft Power Platform]
    PA[Power Apps\n(Canvas App)]
    DV[(Dataverse\nTables + Security Roles)]
    FA[Power Automate\n(Reporting & Notifications)]
  end

  subgraph M365[Microsoft 365]
    OUT[Outlook Connector\n(Email Notifications)]
  end

  A --> PA
  D --> PA
  R --> PA
  C --> PA

  PA <--> DV
  PA --> FA
  FA --> DV
  FA --> OUT
