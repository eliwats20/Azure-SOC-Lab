# Azure-SOC-Lab
<img src="./SOC%20Architecture/Azure%20SOC%20Diagram.png" height= "500" width="500">
Figure 1: Azure SOC Architecture Diagram

🔄 Data Flow Explanation The diagram above shows how telemetry moves through the Azure **SOC** pipeline:

## Windows VM (Endpoint)  

Generates Heartbeat and SecurityEvent logs.

## Azure Monitor Agent (AMA)  

Collects logs and forwards them based on DCRs.

## Data Collection Rules (DCRs)  

Define what logs are collected and where they go.

## Log Analytics Workspace (LAW)  

Stores all ingested logs and enables **KQL** queries.

## Microsoft Sentinel  

Connects to **LAW**, runs analytics rules, and creates incidents.

## Analytics Rules  

Detect suspicious activity (e.g., brute‑force attempts).

## Incidents  

Automatically generated alerts with investigation details.

## KQL Investigation  

Analysts query **LAW** tables to validate and analyze events.
