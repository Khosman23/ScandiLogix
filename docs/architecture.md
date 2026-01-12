# Architecture – ScandiLogix

This document describes the architecture of the ScandiLogix Power Platform solution and how its components work together.

---

## High-Level Architecture

ScandiLogix follows a standard Power Platform architecture:

Power Apps (UI) → Dataverse (Data + Security) → Power Automate (Automation) → Microsoft 365 (Notifications)

```mermaid
flowchart LR

  subgraph Users
    A[Admin]
    D[Dispatcher]
    R[Driver]
    C[Customer]
  end

  subgraph PowerPlatform[Microsoft Power Platform]
    PA[Power Apps Canvas App]
    DV[(Dataverse)]
    FA[Power Automate]
  end

  subgraph M365[Microsoft 365]
    OUT[Outlook Connector]
  end

  A --> PA
  D --> PA
  R --> PA
  C --> PA

  PA <--> DV
  PA --> FA
  FA --> DV
  FA --> OUT
