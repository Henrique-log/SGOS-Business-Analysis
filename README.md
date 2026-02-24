# SGOS-Business-Analysis
Business Analysis project modeling AS-IS and TO-BE processes, defining requirements, business rules and KPIs for a Service Management System.

# Business Analysis Case – Sistema de Gestão de Ordens de Serviço (SGOS)

## Autor
Henrique Santos da Silva  
Data: Fevereiro/2026  
Versão: 1.0  

---

## Introdução
O projeto apresenta uma análise de negócio para o Sistema de Gestão de Ordens de Serviço (SGOS), com objetivo de otimizar processos, reduzir retrabalho e melhorar a eficiência operacional.

---

## Stakeholders
- **Técnicos de Manutenção:** execução e organização  
- **Supervisor:** distribuição e controle de SLA  
- **Gerente Operacional:** redução de custos  
- **Diretoria:** indicadores consolidados  
- **Equipe de TI:** implantação e viabilidade técnica  

---

## Objetivo
Desenvolver um processo estruturado para controle de ordens de serviço, priorização automática e monitoramento de SLA, com dashboard gerencial de KPIs.

---

## Processos

### AS IS – Processo Atual

```mermaid
flowchart TD
A([Início]) --> B[Equipamento apresenta falha]
B --> C[Técnico comunica supervisor verbalmente]
C --> D[Supervisor registra em planilha manual]
D --> E{Equipamento é crítico?}

E -- Sim --> F[Definir prioridade alta manualmente]
E -- Não --> G[Definir prioridade normal]

F --> H[Execução da manutenção]
G --> H

H --> I[Registro incompleto ou tardio]
I --> J[Sem controle de SLA]
J --> K([Fim])
