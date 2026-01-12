# Security Model – ScandiLogix

This document describes the role-based security model implemented in the ScandiLogix solution using Microsoft Dataverse security roles.

The security model follows the **least-privilege principle** and is designed to support enterprise-grade access control.

---

## Security Principles

- Role-based access control (RBAC)
- Least-privilege by default
- Separation of operational responsibilities
- Data access enforced at the Dataverse level
- UI behavior aligned with security roles

---

## Defined Roles

### Admin
**Access level:** Full

**Permissions:**
- Full access to all tables
- User and role management
- Configuration and administrative operations

**Purpose:**
- System administration
- Environment and data governance

---

### Dispatcher
**Access level:** Operational management

**Permissions:**
- Read and update Shipments
- Assign Drivers to Shipments
- View Incidents
- No access to administrative configuration

**Purpose:**
- Manage daily logistics operations
- React to incidents and delays

---

### Driver
**Access level:** Limited operational access

**Permissions:**
- Read assigned Shipments only
- Create Incidents for assigned Shipments
- Update shipment status
- No access to other drivers’ or customers’ data

**Purpose:**
- Report shipment progress and incidents
- Minimize UI complexity and data exposure

---

### Customer
**Access level:** Read-only (own data)

**Permissions:**
- Read own Shipments
- Read Incidents related to own Shipments
- No access to operational or internal data

**Purpose:**
- Transparency and shipment visibility
- Prepared for future self-service portals and Copilot integration

---

## Enforcement Mechanisms

- Dataverse Security Roles control table-level access
- Lookup-based filtering ensures users only see related records
- App logic respects role-based visibility
- No business-critical security enforced only at UI level

---

## Security Benefits

- Prevents unauthorized data access
- Reduces risk of accidental data modification
- Aligns with enterprise and public-sector requirements
- Supports future scaling with minimal rework

