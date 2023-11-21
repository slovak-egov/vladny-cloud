|||||
| - | - | :- | :- |
|Konvencie pomenovania a označovania zdrojov v eSKa Cloud Azure||||
|Sledovací list||||
|Author:|Roman Gelien|||
|Date:|01\.09.2022|||
|||||
|Inštrukcie:|Táto tabuľka slúži na zaznamenávanie zmien. Každá zmena musí byť prediskutovaná s Cloudovým oddelením na MIRRI a po schválení bude následne zahrnutá alebo pridaná do dokumentu.|||
|||||
|**História zmien**||||
|**Verzia**|**Dátum**|||
|1|01\.10.2022|||
|||||
|||||


|||
| - | - |
|||
|||
|||
|||
|||
|||
|||
|||
|**Meno**|**Hárok**|
|Roman Gelien|Naming Convention Central, Spoke Tagging Convention|
|||
|||


|||
| - | - |
|||
|||
|||
|||
|||
|||
|||
|||
|**Zmeny - komentáre**||
|Prvotný dokument - základne zdroje a tagy identifikovane a schválene.||
|||
|||


|Konvencia pomenovania Centrálnej časti||||
| - | :- | :- | :- |
|Inštrukcie:|Tento hárok použite na definovanie štandardov pomenovávania, ktoré chcete použiť na každý typ prostriedku, ktorý plánujete nasadiť.|||
|||||
|**Pomenovanie komponentov**|Hlavné časti kontextu, ktoré sa použijú na zostavenie názvov zdrojov.|||
|**Komponent pomenovania**|**Popis**|||
|Typ predplatného/subskripcie|Súhrnný popis účelu predplatného obsahujúceho zdroj. Často rozdelené podľa typu prostredia nasadenia alebo špecifických pracovných zaťažení.|||
|Prostredie nasadenia|Zaradenie vývoja pracovných zaťažení, ktoré zdroj podporuje.|||
|Pripojenie prostredia|Pripojenie do GovNet uzla|||
|Región|Oblasť Azure, kde je prostriedok nasadený.|||
|||||
|**Management Group**||||
|**Asset type**|**Scope**|||
|Management Group|Account OVM|||
|||||
|**Subscriptions**||||
|**Asset type**|**Scope**|||
|Subscription|Account/Enterprise Agreement|||
|||||
|**Resource groups**||||
|**Asset type**|**Scope**|||
|Resource Group|Subscription|||
|||||
|**Virtual Networking Central**||||
|**Asset type**|**Scope**|||
|Virtual WAN Central|Resource group|||
|Virtual HUB Central|Resource group|||
|Virtual Network Central|Resource group|||
|Vnet virtual gateway|Virtual network|||
|Site to site connections|Resource group|||



|VNet Connections|Resource group|
| - | - |
|Subnet|Virtual network|
|NSG|Subnet or NIC|
|Public IP|Resource group|
|Private Endpoint|Resource group|
|Load Balancer|Resource group|
|Application Gateway|Virtual gateway|
|Application Security Group (ASG)|Subnet or NIC|
|User Defined Routes (UDR)|Resource group|
|Route Table|Resource group|
|Firewall|Virtual network|
|Firewall Policy|Virtual network|
|Network Rules|Firewall Policy Rule|
|Application Rules|Firewall Policy Rule|
|DNAT Rules|Firewall Policy Rule|
|Web Application Firewall|Virtual network|
|Azure Virtual Desktop|Virtual network|
|Bastion|Virtual network|
|DNS private zone custom|Resource group|
|DNS private zone central|Resource group|
|DNS private link|Resource group|
|||
|**Virtual Networking Spoke**||
|Virtual Network Spoke|Resource group|
|Subnet|Virtual network|
|Azure Virtual Desktop|Virtual network|
|Bastion|Virtual network|
|||
|**Virtual Machines**||
|**Asset type**|**Scope**|
|Virtual Machine|Resource group|
|VM Scale Set|Resource group|
|VM Availability Set |Resource group|
|Manage Disks|Resource group|
|VM Storage account|Global|
|DNS Label|Global|
|Load Balancer|Resource group|
|NIC|Resource group|
|||
|**Kubernetes Services AKS**||
|**Asset type**|**Scope**|



|AKS Cluster|Resource group|
| - | - |
|Container Instances|Resource group|
|Container Registry|Resource group|
|||
|**VMware Services SDDC**||
|**Asset type**|**Scope**|
|VMware Services SDDC|Global|
|||
|**Storage**||
|**Asset type**|**Scope**|
|Azure Storage account - general use|Global|
|Azure Storage account - diagnostic logs|Global|
|||
|**Security**||
|**Asset type**|**Scope**|
|Key Vault|Resource group|
|HSM|Resource group|
|||
|**Security**||
|**Asset type**|**Scope**|
|Managed identity|Resource group|
|Terraform identity|Managed identity|
|||
|**PaaS Services**||
|**Asset type**|**Scope**|
|App Service|Global|
|Function App|Global|
|Cloud Services|Global|
|||
|**Service Bus**||
|**Asset type**|**Scope**|
|Service Bus|Global|
|Service Bus queues|Service Bus|
|||
|**AI + Machine Learning**||
|**Asset type**|**Scope**|
|Azure Search|Global|
|Cognitive Services|Resource group|
|ChatGPT|Resource group|
|Azure Machine Learning workspace|Resource group|
|||


|**Analytics**||
| - | - |
|**Asset type**|**Scope**|
|Azure Data Factory|Global|
|Azure Data Lake Storage|Global|
|Azure Data Bricks|Global|
|Azure Data Lake Analytics|Global|
|Power BI Embedded|Global|
|HDInsight - Spark|Global|
|HDInsight - Hadoop|Global|
|HDInsight - R server|Global|
|HDInsight - HBase|Global|
|||
|**Internet of Things**||
|**Asset type**|**Scope**|
|Event Hub|Resource group|
|Event Hub Namespace|Resource group|
|Notification Hub|Resource group|
|Notification Hub Namespace|Global|
|Azure Stream Analytics on IoT Edge|Resource group|
|Azure IoT Hub|Global|



||
| - |
||
||
||
|**Príklady**|
|*prod, dev, test, sharedservices*|
|*prod, nonprod*|
|*govnet, nogovnet*|
|*Netherlands Amsterdam <westeu> Ireland Dublin <northeu> Poland Central<centeu>*|
||
||
|**Format**|
|mgmt-<OVM>-<prostredie>|
||
||
|**Format**|
|sub-<služba/aplikácia/projekt>-<prostredie>-<###>|
||
||
|**Format**|
|rg-<služba/aplikácia>-<prostredie>-<region>|
||
||
|**Format**|
|vwan-<služba/aplikácia>-<govnet pripojenie>-<prostredie>-<region>|
|vhub-<služba/aplikácia>-<govnet pripojenie>-<prostredie>-<region>-[###]|
|vnet-<služba/aplikácia>-[OR]-<govnet pripojenie>-<prostredie>-<region>|
|vgw-dmz-<prostredie>-<region>-<###>|
|cn-<prostredie1>-<OR/lokalita1>-to-<prostredie2>-<OR/lokalita2>|



|cn-<lokalGW>-to-<virtualGW>|
| - |
|snet-<účel/služba/aplikácia>-<prostredie>-<region><###>|
|nsg-<policy rule>-<služba/aplikácia>-<prostredie>|
|pip-<služba><##>-<služba/aplikácia>-<prostredie>-<region>-<###>|
|pe-<služba/aplikácia/projekt>-<špecifikácia>-<prostredie>-nic|
|lb-<služba/aplikácia>-<prostredie>-<region>-[špecifikácia]<###>|
|appgw-<služba/aplikácia>-<prostredie>-<region>-[špecifikácia]<###>|
|asg-<služba/aplikácia>-<prostredie>-<špecifikácia> |
|udr-<účel/služba/aplikácia/projekt>-<prostredie>-<###>|
|route-<služba>-<aplikácia/projekt>-<prostredie>-[špecifikácia]<###>|
|AzureFirewall\_vhub-<služba/aplikácia>-<govnet pripojenie>-<prostredie>-<region>|
|fwp-<služba/aplikácia>-<govnet pripojenie>-<prostredie>-<region>|
|net-rule-<služba>-<allow/denied>|
|app-rule-<služba>-<allow/denied>|
|dnat-rule-<služba>-<allow/denied>|
|waf-<služba/aplikácia>-<prostredie>-<region>-[špecifikácia]<###>|
|avd-<účel/služba/aplikácia/projekt>-<prostredie>-<region>-<###>|
|bas-<účel/služba/aplikácia/projekt>-<prostredie>-<region>-<###>|
|<doména>.sk|
|https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-dns|
|dnslink-<názov vnety>|
||
||
|vnet-<služba/aplikácia/projekt>-<prostredie>-<region>|
|snet-<projekt>-<prostredie>-<účel/služba/aplikácia>|
|avd-<účel/služba/aplikácia/projekt>-<prostredie>-<region>-<###>|
|bas-<účel/služba/aplikácia/projekt>-<prostredie>-<region>-<###>|
||
||
|**Format**|
|vcm-<služba/aplikácia/projekt>-<prostredie>-<region>-[špecifikácia]-<###>|
|vmss-<meno setu pre vm>|
|vmas-<služba/aplikácia/projekt>-<špecifikácia>-<prostredie>|
|disk-<služba/aplikácia/projekt>-<prostredie>-<region>-[špecifikácia]-<###>|
|sta-<služba/aplikácia>-<prostredie><###>|
|<A record of vm>.[<region>.cloudapp.azure.com]|
|lb-<služba/aplikácia>-<prostredie>-<region>-[špecifikácia]<###>|
|nic-<##>-<vmname>-<prostredie>-<region>-[špecifikácia]<###>|
||
||
|**Format**|



|aks-{vnet}-<meno aks clustra>-<prostredie>-<region>-<###> |
| - |
|ci-<meno aks clustra>-<###>|
|cr-{vnet}-<meno aks clustra><###>|
||
||
|**Format**|
|sddc-<meno vCenter>-<region>|
||
||
|**Format**|
|stg<služba/aplikácia/projekt><###>|
|stdiag<služba/aplikácia/projekt>-<region><###>|
||
||
|**Format**|
|keyv-<služba/aplikácia/projekt>-<prostredie><###>|
|hsm-<OVM>|
||
||
|**Format**|
|id-<služba/aplikácia/projekt>-<prostredie>-<###>|
|svc-trf-<služba/aplikácia/projekt>-<prostredie>|
||
||
|**Format**|
|azapp-<služba/aplikácia>-<prostredie><###>.[{azurewebsites.net}]|
|azfun-<služba/aplikácia>-<prostredie><###>.[{azurewebsites.net}]|
|azcs-<služba/aplikácia>-<prostredie><###>.[{cloudapp.net}]|
||
||
|**Format**|
|sb-<služba/aplikácia>-<prostredie><###>.[{servicebus.windows.net}]|
|sbq-<popis dopytu>|
||
||
|**Format**|
|srch-<služba/aplikácia>-<prostredie>|
|cs-<služba/aplikácia>-<prostredie>|
|chatgpt-<služba/aplikácia/projekt>-[OR]-<prostredie>-<region>|
|aml-<služba/aplikácia>-<prostredie>-<region>-<###>|
||


||
| - |
|**Format**|
|adf-<služba/aplikácia/projekt>-<OR>-<prostredie>-<region>-<###>|
|dls<služba/aplikácia/projekt/OR><###>|
|dbx-<služba/aplikácia/projekt>-<OR>-<prostredie>-<region>-<###>|
|dla<služba/aplikácia>-<prostredie>-<region>-<###>|
|pbiemb-<služba/aplikácia/projekt>-<OR>-<prostredie>-<region>-<###>|
|hdis-<služba/aplikácia>-<prostredie>-<region>-<###>|
|hdihd-<služba/aplikácia>-<prostredie>-<region>-<###>|
|hdir-<služba/aplikácia>-<prostredie>-<region>-<###>|
|hdihb-<služba/aplikácia>-<prostredie>-<region>-<###>|
||
||
|**Format**|
|evh-queue-<prostredie>-<topic>-<text format>|
|evhns-<služba/aplikácia/OR>-<prostredie>-<region>-<###>|
|anh-<služba/aplikácia/OR>-<prostredie>-<region>-<###>|
|anhns-<služba/aplikácia/OR>-<prostredie>-<region>-<###>|
|asa-<služba/aplikácia>-<prostredie>-<region>-<###>|
|aih-<služba/aplikácia>-<prostredie>-<region>-<###>|



||
| - |
||
||
||
||
||
||
||
||
||
||
|**Example**|
|mgmt-mirri-prod mgmt-mirri-nonprod|
||
||
|**Example**|
|sub-itam-prod-001|
||
||
|**Example**|
|rg-itam-prod-westeu|
||
||
|**Example**|
|vwan-hub-gov-prod-westeu|
|vhub-hub-nogov-prod-westeu|
|vnet-dmz-nogov-prod-westeu|
|vgw-dmz-prod-001|
|cn-prod-mirrisr-to-nonprod-mvsr|



|cn-mvsr-to-mirrisr|
| - |
|snet-sharedservices-prod-westeu-001|
|nsg-weballow-prod|
|pip-appgw1-shared-westeu-001|
|pep-itam-sql-prod-nic|
|lb-itam-sql-prod-westeu-001|
|appgw-itam-web01-prod-westeu-001|
|asg-web01-prod-frontend\_web|
|udr-internet-prod-001|
|route-appgw-itam-prod-001|
|AzureFirewall\_vhub-hub-nogovnet-prod-westeu|
|fwp-hub-nogovnet-prod-westeu|
|net-rule-internet-allow|
|app-rule-banweb-deny|
|dnat-rule-ms-deny|
|waf-web01-prod-westeu-001|
|avd-itam-prod-westeu-001|
|bas-itam-prod-westeu-001|
|itam.sk|
|privatelink.database.windows.net|
|dnslink-kav-mirri-dev-northeu|
||
||
|vnet-itam-prod-westeu|
|snet-itam-prod-sql|
|avd-itam-prod-westeu-001|
|bas-itam-prod-westeu-001|
||
||
|**Example**|
|vcm-itam-prod-westeu-sql-001|
|vmss-vcm-itam-prod-westeu-sql|
|vmas-itam-sql-prod|
|disk-itam-prod-westeu-sql-db-001|
|sta-itam-prod-001|
|web1.eastus2.cloudapp.azure.com|
|lb-itam-prod-westeu-sql-001|
|nic-01-vcm-itam-nonprod-westeu-inv-001|
||
||
|**Example**|



|aks-mirri-prod-westeu-001|
| - |
|ci-mirri-001|
|cr-mirri-001|
||
||
|**Example**|
|sddc-vcmirri-westeu|
||
||
|**Example**|
|stgkav001|
|stdiagkav-westeu001|
||
||
|**Example**|
|keyv-kav-prod-001|
|hsm-mirrisr|
||
||
|**Example**|
|id-kav-prod-001|
|svc-trf-metais-prod|
||
||
|**Example**|
|azapp-navigator-prod-001.azurewebsites.net|
|azfun-navigator-prod-001.azurewebsites.net|
|azcs-navigator-prod-001.azurewebsites.net|
||
||
|**Example**|
|sb-navigator-prod|
|sbq-messagequery|
||
||
|**Example**|
|srch-navigator-prod|
|cs-navigator-prod|
|chatgpt-metais-prod-westeu|
|aml-navigator-prod-westeu|
||


||
| - |
|**Example**|
|adf-kav-mirri-prod-westeu-001|
|dlskavmirriprod001|
|dbx-kav-mirri-prod-westeu-001|
|dlakavmirriprod-westeu-001|
|pbiem-kav-mirri-prod-westeu-001|
|hdis-navigator-prod-westeu-001|
|hdihd-hadoop-prod-westeu-001|
|hdir-navigator-prod-westeu-001|
|hdihb-navigator-prod-westeu-001|
||
||
|**Example**|
|evh-queue-egov-form-json|
|evhns-metais-shared-northeu-001|
|anh-mirri-shared-northeu-001|
|anhns-mirri-shared-northeu-001|
|asa-navigator-prod-westeu-001|
|aih-navigator-prod-westeu-001|



|Konvencia pomenovania OVM časti||||
| - | :- | :- | :- |
|Inštrukcie:|Tento hárok použite na definovanie štandardov pomenovávania, ktoré chcete použiť na každý typ prostriedku, ktorý plánujete nasadiť.|||
|||||
|**Pomenovanie komponentov**|Hlavné časti kontextu, ktoré sa použijú na zostavenie názvov zdrojov.|||
|**Komponent pomenovania**|**Popis**|||
|Typ predplatného/subskripcie|Súhrnný popis účelu predplatného obsahujúceho zdroj. Často rozdelené podľa typu prostredia nasadenia alebo špecifických pracovných zaťažení.|||
|Prostredie nasadenia|Zaradenie vývoja pracovných zaťažení, ktoré zdroj podporuje.|||
|Región|Oblasť Azure, kde je prostriedok nasadený.|||
|||||
|**Virtual Machines**||||
|**Asset type**|**Scope**|||
|Virtual Machine|Resource group|||
|VM Scale Set|Resource group|||
|VM Availability Set |Resource group|||
|Manage Disks|Resource group|||
|VM Storage account|Global|||
|DNS Label|Global|||
|Load Balancer|Resource group|||
|NIC|Resource group|||
|||||
|**Kubernetes Services AKS**||||
|**Asset type**|**Scope**|||
|AKS Cluster|Resource group|||
|Container Instances|Resource group|||
|Container Registry|Resource group|||
|||||
|**VMware Services SDDC**||||
|**Asset type**|**Scope**|||
|VMware Services SDDC|Global|||
|||||
|**Storage**||||
|**Asset type**|**Scope**|||
|Azure Storage account - general use|Global|||
|Azure Storage account - diagnostic logs|Global|||
|||||


|**Security**||
| - | - |
|**Asset type**|**Scope**|
|Key Vault|Resource group|
|HSM|Resource group|
|||
|**Security**||
|**Asset type**|**Scope**|
|Managed identity|Resource group|
|Terraform identity|Managed identity|
|||
|**Databases**||
|**Asset type**|**Scope**|
|Azure SQL Database|Global|
|Azure Cosmos DB (Document Database)|Global|
|Azure Cache for Redis|Global|
|Azure Database for MySQL|Global|
|SQL Data Warehouse|Global|
|SQL Server Stretch Database|Azure SQL Database|
|||
|**PaaS Services**||
|**Asset type**|**Scope**|
|App Service|Global|
|Function App|Global|
|Cloud Services|Global|
|||
|**Service Bus**||
|**Asset type**|**Scope**|
|Service Bus|Global|
|Service Bus queues|Service Bus|
|||
|**AI + Machine Learning**||
|**Asset type**|**Scope**|
|Azure Search|Global|
|Cognitive Services|Resource group|
|ChatGPT|Resource group|
|Azure Machine Learning workspace|Resource group|
|||
|**Analytics**||
|**Asset type**|**Scope**|
|Azure Data Factory|Global|
|Azure Data Lake Storage|Global|



|Azure Data Bricks|Global|
| - | - |
|Azure Data Lake Analytics|Global|
|Power BI Embedded|Global|
|HDInsight - Spark|Global|
|HDInsight - Hadoop|Global|
|HDInsight - R server|Global|
|HDInsight - HBase|Global|
|||
|**Internet of Things**||
|**Asset type**|**Scope**|
|Event Hub|Global|
|Notification Hub|Resource group|
|Notification Hub Namespace|Global|
|Azure Stream Analytics on IoT Edge|Resource group|
|Azure IoT Hub|Global|



||
| - |
||
||
||
|**Príklady**|
|*prod, dev, test, sharedservices*|
|*prod, nonprod*|
|*Netherlands Amsterdam <westeu> Ireland Dublin <northeu> Poland Central<centeu>*|
||
||
|**Format**|
|vcm-<služba/aplikácia/projekt>-<prostredie>-<region>-[špecifikácia]-<###>|
|vmss-<meno setu pre vm>|
|vmas-<služba/aplikácia/projekt>-<špecifikácia>-<prostredie>|
|disk-<služba/aplikácia/projekt>-<prostredie>-<region>-[špecifikácia]-<###>|
|sta-<služba/aplikácia>-<prostredie><###>|
|<A record of vm>.[<region>.cloudapp.azure.com]|
|lb-<služba/aplikácia>-<prostredie>-<region>-[špecifikácia]<###>|
|nic-<##>-<vmname>-<prostredie>-<region>-[špecifikácia]<###>|
||
||
|**Format**|
|aks-{vnet}-<meno aks clustra>-<prostredie>-<region>-<###> |
|ci-<meno aks clustra>-<###>|
|cr-{vnet}-<meno aks clustra><###>|
||
||
|**Format**|
|sddc-<meno vCenter>[###]-<region>|
||
||
|**Format**|
|stg<služba/aplikácia/projekt><###>|
|stdiag<služba/aplikácia/projekt>-<region><###>|
||


||
| - |
|**Format**|
|keyv-<služba/aplikácia/projekt>-<prostredie><###>|
|hsm-<OVM>|
||
||
|**Format**|
|id-<služba/aplikácia/projekt>-<prostredie>-<###>|
|svc-<služba/aplikácia>-<zdroj>-<projekt>-<prostredie>|
||
||
|**Format**|
|sqldb-<názov databázy>-<prostredie>|
|cosdb-<App Name>-<Environment>|
|redis-<App Name>-<Environment>|
|mysql-<App Name>-<Environment>|
|sqldw-<App Name>-<Environment>|
|sqlstrdb-<App Name>-<Environment>|
||
||
|**Format**|
|azapp-<služba/aplikácia>-<prostredie><###>.[{azurewebsites.net}]|
|azfun-<služba/aplikácia>-<prostredie><###>.[{azurewebsites.net}]|
|azcs-<služba/aplikácia>-<prostredie><###>.[{cloudapp.net}]|
||
||
|**Format**|
|sb-<služba/aplikácia>-<prostredie><###>.[{servicebus.windows.net}]|
|sbq-<popis dopytu>|
||
||
|**Format**|
|srch-<služba/aplikácia>-<prostredie>|
|cs-<služba/aplikácia>-<prostredie>|
|chatgpt-<služba/aplikácia/projekt>-[OR]-<prostredie>-<region>|
|aml-<služba/aplikácia>-<prostredie>-<region>-<###>|
||
||
|**Format**|
|adf-<služba/aplikácia/projekt>-<OR>-<prostredie>-<region>-<###>|
|dls<služba/aplikácia/projekt/OR><###>|



|dbx-<služba/aplikácia/projekt>-<OR>-<prostredie>-<region>-<###>|
| - |
|dla<služba/aplikácia>-<prostredie>-<region>-<###>|
|pbiemb-<služba/aplikácia/projekt>-<OR>-<prostredie>-<region>-<###>|
|hdis-<služba/aplikácia>-<prostredie>-<region>-<###>|
|hdihd-<služba/aplikácia>-<prostredie>-<region>-<###>|
|hdir-<služba/aplikácia>-<prostredie>-<region>-<###>|
|hdihb-<služba/aplikácia>-<prostredie>-<region>-<###>|
||
||
|**Format**|
|evh-<služba/aplikácia/OR>-<prostredie>-<region>-<###>|
|anh-<služba/aplikácia/OR>-<prostredie>-<region>-<###>|
|anhns-<služba/aplikácia/OR>-<prostredie>-<region>-<###>|
|asa-<služba/aplikácia>-<prostredie>-<region>-<###>|
|aih-<služba/aplikácia>-<prostredie>-<region>-<###>|



||
| - |
||
||
||
||
||
||
||
||
||
|**Example**|
|vcm-itam-prod-westeu-sql-001|
|vmss-vcm-itam-prod-westeu-sql|
|vmas-itam-sql-prod|
|disk-itam-prod-westeu-sql-db-001|
|sta-itam-prod-001|
|web1.eastus2.cloudapp.azure.com|
|lb-itam-prod-westeu-sql-001|
|nic-01-vcm-itam-nonprod-westeu-inv-001|
||
||
|**Example**|
|aks-mirri-prod-westeu-001|
|ci-mirri-001|
|cr-mirri-001|
||
||
|**Example**|
|sddc-vcmirri-westeu|
||
||
|**Example**|
|stgkav001|
|stdiagkav-westeu001|
||


||
| - |
|**Example**|
|keyv-kav-prod-001|
|hsm-mirrisr|
||
||
|**Example**|
|id-kav-prod-001|
|svc-trf-metais-prod / svc-aks-lb-metais-prod|
||
||
|**Example**|
|sqldb-navigator-prod|
|cosdb-navigator-prod|
|redis-navigator-prod|
|mysql-navigator-prod|
|sqldw-navigator-prod|
|sqlstrdb-navigator-prod|
||
||
|**Example**|
|azapp-navigator-prod-001.azurewebsites.net|
|azfun-navigator-prod-001.azurewebsites.net|
|azcs-navigator-prod-001.azurewebsites.net|
||
||
|**Example**|
|sb-navigator-prod|
|sbq-messagequery|
||
||
|**Example**|
|srch-navigator-prod|
|cs-navigator-prod|
|chatgpt-metais-prod-westeu|
|aml-navigator-prod-westeu|
||
||
|**Example**|
|adf-kav-mirri-prod-westeu-001|
|dlskavmirriprod001|



|dbx-kav-mirri-prod-westeu-001|
| - |
|dlakavmirriprod-westeu-001|
|pbiem-kav-mirri-prod-westeu-001|
|hdis-navigator-prod-westeu-001|
|hdihd-hadoop-prod-westeu-001|
|hdir-navigator-prod-westeu-001|
|hdihb-navigator-prod-westeu-001|
||
||
|**Example**|
|evh-mirri-shared-northeu-001|
|anh-mirri-shared-northeu-001|
|anhns-mirri-shared-northeu-001|
|asa-navigator-prod-westeu-001|
|aih-navigator-prod-westeu-001|



|Konvencia pomenovania Taggov||
| - | :- |
|Inštrukcie:||
|||
|**Tag Name**||
|DataClassification ||
|Criticality ||
|OrgRiadenia ||
|ProjectName ||
|OpsTeam ||
|Environment ||
|Owner ||
|Start projektu ||
|MetaIS||
|Koniec projektu ||
|Runtime ||



||
| - |
|Tento hárok použite na definovanie značiek metadát, ktoré chcete použiť na zdroje.|
||
|**Description**|
|Klasifikácia citlivosti dát / NBU |
|Kritickosť služby/aplikácie vychádzajúca z SLA |
|Organ verejnej moci |
|Názov projektu pod ktorým sú služby/aplikácie dodávane |
|Názov IT ops teamu podľa organizačnej štruktúry |
|Prostredie kde služba/aplikácia beží |
|e-mail osoby zodpovednej za službu/aplikáciu |
|Dátum začiatku určuje časovú os projektu|
|Identifikátor ISVS|
|Dátum konca určuje časovú os projektu|
|Automatické vypínanie/zapínanie resources pomocou tags den/noc/vikend/sviatok |



|||
| - | - |
|||
|||
|**Key**|**Example Value**|
|*Classification*|*Verejne, Dôverne, Tajne, Prísne Tajne* |
|*Criticality*|*Nízka, Stredná, Vysoká, Kritická* |
|*Org*|*MVSR, NASES, MIRRISR* |
|*Project Name*|*Metais\_XXXX - costcenter* |
|*Operations*|*CloudTeam* |
|*Subscription*|*Prod, NonProd* |
|*Stakeholder*|*meno@mirri.gov.sk* |
|*StartDate*|*{dd.mm.yyyy}*|
|*Kód ISVS*|*projekt\_XXXX*|
|*EndDate*|*{dd.mm.yyyy}*|
|*StartTime EndTime*|*Start [06:00][Day] End [17:00][Day]*|



||
| - |
||
||
|**Required?**|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*Yes*|
|*No*|

