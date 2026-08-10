# Azure-SOC-Lab
<img src="./SOC%20Architecture/Azure%20SOC%20Diagram.png" height= "500" width="500">
Figure 1: Azure SOC Architecture Diagram

🔄 Data Flow Explanation The diagram above shows how telemetry moves through the Azure **SOC** pipeline:

1. Windows VM (Endpoint)  

Generates Heartbeat and SecurityEvent logs.

2. Azure Monitor Agent (AMA)  

Collects logs and forwards them based on DCRs.

3. Data Collection Rules (DCRs)  

Define what logs are collected and where they go.

4. Log Analytics Workspace (LAW)  

Stores all ingested logs and enables **KQL** queries.

5. Microsoft Sentinel  

Connects to **LAW**, runs analytics rules, and creates incidents.

6. Analytics Rules  

Detect suspicious activity (e.g., brute‑force attempts).

7. Incidents  

Automatically generated alerts with investigation details.

8. KQL Investigation  

Analysts query **LAW** tables to validate and analyze events.
