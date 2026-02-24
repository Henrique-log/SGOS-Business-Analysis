# SGOS – Business Analysis Case

Business Analysis project modeling AS-IS and TO-BE processes, defining requirements, business rules and KPIs for a Service Management System.

---

## Author
Henrique Santos da Silva  
Date: February/2026  
Version: 1.0  

---

## Introduction
This project presents a Business Analysis case for a Service Management System (SGOS), aiming to optimize operational processes, reduce rework and improve efficiency through structured workflow modeling and SLA monitoring.

---

## Stakeholders
- **Maintenance Technicians** – execution and operational activities  
- **Supervisor** – task distribution and SLA control  
- **Operational Manager** – cost reduction and performance monitoring  
- **Board of Directors** – strategic indicators and decision-making support  
- **IT Team** – system implementation and technical feasibility  

---

## Objective
Develop a structured service order management process including automatic prioritization, SLA monitoring and a management dashboard with key performance indicators (KPIs).

---

## Scope

### In Scope
- Equipment registration  
- Service order creation  
- Automatic priority classification  
- Mandatory execution record  
- SLA monitoring  
- Management dashboard  

### Out of Scope
- ERP integration  
- Inventory management module  

---

## Functional Requirements
- Equipment registration module  
- Service order creation  
- Mandatory execution logging  
- Automatic priority classification  
- Management dashboard with KPIs  

---

## Business Rules
- Critical service orders must be handled within 4 hours (SLA)  
- Delayed service orders must trigger automatic notifications  
- Service orders cannot be closed without complete execution records  

---

## Processes

### AS-IS – Current Process

```mermaid
flowchart TD
A([Start]) --> B[Equipment failure identified]
B --> C[Technician informs supervisor verbally]
C --> D[Supervisor registers request manually in spreadsheet]
D --> E{Is the equipment critical?}

E -- Yes --> F[Define high priority manually]
E -- No --> G[Define normal priority]

F --> H[Maintenance execution]
G --> H

H --> I[Incomplete or delayed record]
I --> J[No SLA monitoring]
J --> K([End])
