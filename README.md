# Azure-SOC-Lab
<img src="./SOC%20Architecture/Azure%20SOC%20Diagram.png" height= "500" width="500">
Figure 1: Azure SOC Architecture Diagram  

# Architecture Diagram Description  
🔄 Data Flow Explanation 

The diagram above shows how telemetry moves through the Azure **SOC** pipeline:

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

# 📦 Prerequisites
Before deploying the Azure SOC Monitoring Lab, ensure the following requirements are met.

### Azure Requirements
- Active Azure subscription
- Ability to create and manage resources (Contributor or higher)
- Resource Group for SOC components
- Outbound internet access for the VM (required for AMA ingestion)

### Licensing Requirements
- Microsoft Sentinel enabled on the Log Analytics Workspace
- Optional: Microsoft Defender for Endpoint (for richer telemetry)
- Subscription must support:
  - Virtual Machines
  - Log Analytics Workspace
  - Azure Monitor Agent
  - Microsoft Sentinel
  - Logic Apps (optional)

### Local Requirements
- Azure **CLI** installed (optional but recommended)
- **RDP** client to access the Windows VM
- Basic familiarity with **KQL** (Kusto Query Language)

### Service Dependencies
- Azure Monitor Agent (AMA) requires:
  - A Data Collection Rule
  - VM access to Azure Monitor ingestion endpoints
  - A linked Log Analytics Workspace

- Data Collection Rules (DCRs) require:
  - Correct subscription + resource group scope
  - Assignment to the VM
  - Output to the correct workspace

- Log Analytics Workspace (LAW) requires:
  - Deployment before enabling Sentinel
  - Proper retention settings
  - Connection to Sentinel
  - Microsoft Sentinel requires:
  - Workspace connection
  - Enabled analytics rules
  - Proper IAM roles (Sentinel Contributor, Log Analytics Contributor)
