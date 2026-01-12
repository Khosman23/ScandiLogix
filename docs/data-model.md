# Data Model – ScandiLogix

This document describes the Dataverse data model used in the ScandiLogix Power Platform solution.  
The data model is designed to support structured logistics workflows, role-based access and future scalability.

---

## Design Principles

- Centralized data storage using Dataverse as the system of record
- Clear ownership and responsibility per entity
- Relational structure using lookup relationships (1:N)
- Prepared for future extensions without breaking existing logic
- Supports role-based security and least-privilege access

---

## Core Entities

### UserAccount
Represents all users of the system and acts as the primary authentication and role reference.

**Key fields:**
- UserAccountId (Primary Key)
- Username
- Role (Admin, Dispatcher, Driver, Customer)
- IsActive

**Purpose:**
- Single entry point for authentication
- Controls role-based navigation and access inside the app

---

### Driver
Stores driver-specific information used in operational workflows.

**Key fields:**
- DriverId (Primary Key)
- Name
- AvailabilityStatus
- UserAccount (Lookup)

**Purpose:**
- Enables driver assignment to shipments
- Separates driver data from general user accounts

---

### Dispatcher
Represents operational staff responsible for managing shipments.

**Key fields:**
- DispatcherId (Primary Key)
- Name
- UserAccount (Lookup)

**Purpose:**
- Supports dispatcher-specific UI and permissions
- Enables role separation without duplicating user data

---

### Customer
Represents business customers receiving shipments.

**Key fields:**
- CustomerId (Primary Key)
- CompanyName
- ContactInformation
- UserAccount (Lookup)

**Purpose:**
- Allows customer-specific shipment visibility
- Supports future customer portals and Copilot scenarios

---

### Shipment
Central business entity representing a logistics shipment.

**Key fields:**
- ShipmentId (Primary Key)
- ShipmentCode
- Status (Planned, Assigned, In Transit, Delayed, Delivered)
- PickupLocation
- DeliveryLocation
- PlannedDeliveryDate
- ActualDeliveryDate
- Driver (Lookup)
- Customer (Lookup)

**Purpose:**
- Single source of truth for shipment status
- Links drivers, customers and incidents together

---

### Incident
Represents exceptions or issues occurring during shipment.

**Key fields:**
- IncidentId (Primary Key)
- IncidentCode
- Type
- Description
- Status (Open, Resolved)
- Timestamp
- Shipment (Lookup)

**Purpose:**
- Structured exception management
- Enables automation, reporting and analytics

---

## Relationships Overview

- UserAccount → Driver (1:1)
- UserAccount → Dispatcher (1:1)
- UserAccount → Customer (1:1)
- Customer → Shipment (1:N)
- Driver → Shipment (1:N)
- Shipment → Incident (1:N)

This relational structure ensures clean separation of concerns while maintaining traceability across all business processes.

---

## Why Dataverse

Dataverse was chosen because it provides:

- Built-in security model (row-level & role-based)
- Strong relational capabilities
- Native integration with Power Apps and Power Automate
- Enterprise-grade scalability and governance
- Support for ALM and solution-based deployments

