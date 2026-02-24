# SGOS – Business Analysis Case

Business Analysis project modeling AS-IS and TO-BE processes, defining requirements, business rules, and KPIs for a Service Management System.

---

## Author
Henrique Santos da Silva  
**Date:** February 2026  
**Version:** 2.0  

---

## Introduction

This project presents a Business Analysis case for a Service Management System (SGOS), aiming to optimize operational processes, reduce rework, and improve efficiency through structured workflow modeling and SLA monitoring.

---

## Problem Statement

The current service order process lacks SLA control, structured prioritization, and proper execution records. This leads to operational inefficiencies, inconsistent task management, and limited performance visibility for leadership.

---

## Stakeholders

- **Maintenance Technicians** – Execution and operational activities.
- **Supervisor** – Task distribution and SLA control.
- **Operational Manager** – Cost reduction and performance monitoring.
- **Board of Directors** – Strategic indicators and decision-making support.
- **IT Team** – System implementation and technical feasibility.

---

## Objective

Develop a structured service order management process including automatic prioritization, SLA monitoring, and a management dashboard with Key Performance Indicators (KPIs), ensuring governance and operational transparency.

---

## Scope

### In Scope
- Equipment registration
- Service order creation
- Automatic priority classification
- Mandatory execution records
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
- Automated SLA breach notifications

---

## Business Rules

- Critical service orders must be handled within 4 hours (SLA).
- Delayed service orders must trigger automatic notifications.
- Service orders cannot be closed without complete execution records.
- Priority must be automatically assigned based on equipment criticality.

---

## Priority Matrix

| Priority | Description | SLA |
|----------|------------|-----|
| High     | Critical equipment failure | 4 hours |
| Medium   | Operational impact | 8 hours |
| Low      | Non-critical issue | 24 hours |

---

# Process Modeling

## Process Modeling – AS-IS and TO-BE

```mermaid
flowchart LR

%% =========================
%% AS-IS PROCESS
%% =========================

subgraph AS-IS [AS-IS – Current Process]
    A1([Start]) --> B1[Equipment failure identified]
    B1 --> C1[Technician informs supervisor verbally]
    C1 --> D1[Supervisor registers request manually in spreadsheet]
    D1 --> E1{Is the equipment critical?}

    E1 -- Yes --> F1[Define high priority manually]
    E1 -- No --> G1[Define normal priority]

    F1 --> H1[Maintenance execution]
    G1 --> H1

    H1 --> I1[Incomplete or delayed record]
    I1 --> J1[No SLA monitoring]
    J1 --> K1([End])
end

%% =========================
%% TO-BE PROCESS
%% =========================

subgraph TO-BE [TO-BE – Proposed Process]
    A2([Start]) --> B2[Equipment failure identified]
    B2 --> C2[Technician opens Service Order in SGOS Mobile/Web]
    C2 --> D2[System automatically assigns priority based on Asset Criticality]
    D2 --> E2{Is it High Priority?}

    E2 -- Yes --> F2[Immediate alert to Supervisor and Available Technician]
    E2 -- No --> G2[Added to standard execution queue]

    F2 --> H2[Maintenance execution with real-time logging]
    G2 --> H2

    H2 --> I2{All mandatory fields filled?}
    I2 -- No --> H2
    I2 -- Yes --> J2[Close Service Order and Stop SLA Timer]

    J2 --> K2[Update Management Dashboard with KPIs]
    K2 --> L2([End])
end
```

This case was developed as part of my Business Analysis portfolio to demonstrate process modeling, requirement definition, and governance-oriented thinking.
