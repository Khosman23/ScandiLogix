# ScandiLogix – Power Platform Solution

ScandiLogix is an enterprise-oriented Power Platform solution built with **Power Apps, Dataverse and Power Automate**.  
The project demonstrates how low-code can be used to design secure, scalable and business-focused solutions following Microsoft Power Platform best practices.

The solution is developed as a portfolio project with a strong focus on **architecture, data modeling, security, automation and Application Lifecycle Management (ALM)**.

---

## Business Problem

Logistics organizations often face challenges such as:

- Fragmented systems for shipment handling and incident reporting  
- Manual processes and limited automation  
- Poor visibility between operational roles  
- Weak access control and unclear data ownership  

ScandiLogix addresses these challenges by providing a **single, role-based application** that supports daily logistics workflows in a structured and secure way.

---

## Solution Overview

ScandiLogix provides:

- A unified Canvas App for logistics and customer service workflows  
- Centralized data storage using Dataverse  
- Automated reporting and notifications with Power Automate  
- Role-based access control (RBAC) following the least-privilege principle  
- A solution-based setup ready for ALM and future environment separation  

---

## My Role

**Power Platform Solution Architect & Developer**

Responsibilities in this project:

- Designed the overall solution architecture  
- Modeled relational data in Dataverse  
- Developed the Canvas App UI and business logic  
- Implemented role-based security using Dataverse security roles  
- Built Power Automate flows for automation and reporting  
- Structured the solution for export as a managed solution  
- Documented architecture, data model and security design  

---

## Key Features

- Customer, Shipment, Incident and User management  
- Dispatcher workflow for assigning drivers to shipments  
- Driver interface for reporting shipment status and incidents  
- Incident tracking linked to individual shipments  
- Automated reporting using Power Automate  
- Role-based UI and data access (Admin, Dispatcher, Driver)  
- Relational Dataverse data model with lookup relationships  

---

## Architecture

High-level architecture:

Power Apps (Canvas App – UI)  
→ Dataverse (relational data layer & security)  
→ Power Automate (automation & reporting)  
→ Microsoft 365 (Outlook connector)

Architecture diagrams are available in the `/assets` folder.

---

## Screenshots & Demo

Screenshots are available in:

`/assets/screenshots`

Including:

- Login screen  
- Admin dashboard  
- Dispatcher assignment view  
- Driver reporting view  
- Dataverse table relationships  
- Power Automate flow overview  

---

## ALM & Best Practices

- Solution-based development for ALM readiness  
- Separation of UI, data and automation  
- Role-based access control using Dataverse security roles  
- Scalable data model designed for future extensions  
- Prepared for Dev/Test/Prod environment separation  

---

## Technologies Used

- Power Apps (Canvas App)  
- Dataverse  
- Power Automate  
- Microsoft 365 connectors  

---

## Next Steps

Planned improvements:

- Extended technical documentation in `/docs`  
- Environment variables for configuration  
- Improved error handling and monitoring  
- Additional automation flows for operational insights  
