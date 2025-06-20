## Menná Konvencia pre Microsoft Azure
- [Skratky OR a prostredi](https://github.com/slovak-egov/vladny-cloud/blob/main/or-naming-convention.md)
- [Konvencia pomenovania Centrálnej časti](https://github.com/slovak-egov/vladny-cloud/blob/main/azure-naming-convention.md#konvencia-pomenovania-centr%C3%A1lnej-%C4%8Dasti)
- [Konvencia pomenovania OR časti](https://github.com/slovak-egov/vladny-cloud/blob/main/azure-naming-convention.md#konvencia-pomenovania-or-%C4%8Dasti)

### Konvencia pomenovania Centrálnej časti

Inštrukcie: Tento hárok použite na definovanie štandardov pomenovávania, ktoré chcete použiť na každý typ prostriedku, ktorý plánujete nasadiť.

#### Management Group                        
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Management Group | Account OVM | mgmt-{OVM}-{prostredie} | mgmt-mirri-prod{br}mgmt-mirri-nonprod |

#### Subscriptions

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Subscription pre projekt | Account/Enterprise Agreement | sub-{služba/aplikácia/projekt}-{prostredie}-{###} | sub-itam-prod-001 |
| Subscription pre sandbox | Account/Enterprise Agreement | sub-sandbox-{organizácia}-{služba/aplikácia/projekt}-{###} | sub-sandbox-mirri-rodnylistobce-001 |

#### Resource groups 

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Resource Group | Subscription | rg-{služba/aplikácia}-{prostredie}-{region} | rg-itam-prod-northeu |

#### Virtual Networking Central

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Virtual WAN Central                     | Resource group                                                                                                                               | vwan-{služba/aplikácia}-{govnet pripojenie}-{prostredie}-{region}                                                                                      | vwan-hub-gov-prod-northeu                    |
| Virtual HUB Central                     | Resource group                                                                                                                               | vhub-{služba/aplikácia}-{govnet pripojenie}-{prostredie}-{region}-[###]                                                                                | vhub-hub-nogov-prod-northeu                  |
| Virtual Network Central                 | Resource group                                                                                                                               | vnet-{služba/aplikácia}-[OR]-{govnet pripojenie}-{prostredie}-{region}                                                                                 | vnet-dmz-nogov-prod-northeu                  |
| Vnet virtual gateway                    | Virtual network                                                                                                                              | vgw-dmz-{prostredie}-{region}-{###}                                                                                                                    | vgw-dmz-prod-001                            |
| Site to site connections                | Resource group                                                                                                                               | cn-{prostredie1}-{OR/lokalita1}-to-{prostredie2}-{OR/lokalita2}                                                                                        | cn-prod-mirrisr-to-nonprod-mvsr             |
| VNet Connections                        | Resource group                                                                                                                               | cn-{lokalGW}-to-{virtualGW}                                                                                                                            | cn-mvsr-to-mirrisr                          |
| Subnet                                  | Virtual network                                                                                                                              | snet-{účel/služba/aplikácia}-{prostredie}-{region}{###}                                                                                                | snet-sharedservices-001         |
| NSG                                     | Subnet or NIC                                                                                                                                | nsg-{policy rule}-{služba/aplikácia}-{prostredie}                                                                                                      | nsg-weballow-prod                           |
| Public IP                               | Resource group                                                                                                                               | pip-{služba}{##}-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                        | pip-appgw1-shared-northeu-001                |
| Private Endpoint                        | Resource group                                                                                                                               | pe-{služba/aplikácia/projekt}-{špecifikácia}-{prostredie}-nic                                                                                          | pep-itam-sql-prod-nic                       |
| Load Balancer                           | Resource group                                                                                                                               | lb-{služba/aplikácia}-{prostredie}-{region}-[špecifikácia]{###}                                                                                        | lb-itam-sql-prod-northeu-001                 |
| Application Gateway                     | Virtual gateway                                                                                                                              | appgw-{služba/aplikácia}-{prostredie}-{region}-[špecifikácia]{###}                                                                                     | appgw-itam-web01-prod-northeu-001            |
| Application Security Group (ASG)        | Subnet or NIC                                                                                                                                | asg-{služba/aplikácia}-{prostredie}-{špecifikácia}                                                                                                     | asg-web01-prod-frontend_web                 |
| User Defined Routes (UDR)               | Resource group                                                                                                                               | udr-{účel/služba/aplikácia/projekt}-{prostredie}-{###}                                                                                                 | udr-internet-prod-001                       |
| Route Table                             | Resource group                                                                                                                               | route-{služba}-{aplikácia/projekt}-{prostredie}-[špecifikácia]{###}                                                                                    | route-appgw-itam-prod-001                   |
| Firewall                                | Virtual network                                                                                                                              | AzureFirewall_vhub-{služba/aplikácia}-{govnet pripojenie}-{OVM}-{prostredie}-{region}                                                                        | AzureFirewall_vhub-hub-nogov-155-prod-northeu |
| Firewall Policy                         | Virtual network                                                                                                                              | fwp-{služba/aplikácia}-{govnet pripojenie/OVM}-{prostredie}-{region}                                                                                       | fwp-hub-nogov-northeu / fwp-155-northeu               |
| Network Rules                           | Firewall Policy Rule                                                                                                                         | net-rule-{služba}-{allow/denied}                                                                                                                       | net-rule-internet-allow                     |
| Application Rules                       | Firewall Policy Rule                                                                                                                         | app-rule-{služba}-{allow/denied}                                                                                                                       | app-rule-banweb-deny                        |
| DNAT Rules                              | Firewall Policy Rule                                                                                                                         | dnat-rule-{služba}                                                                                                                      | dnat-rule-ms                           |
| Web Application Firewall                | Virtual network                                                                                                                              | waf-{služba/aplikácia}-{prostredie}-{region}-[špecifikácia]{###}                                                                                       | waf-web01-prod-northeu-001                   |
| Azure Virtual Desktop                   | Virtual network                                                                                                                              | avd-{účel/služba/aplikácia/projekt}-{prostredie}-{region}-{###}                                                                                        | avd-itam-prod-northeu-001                    |
| Bastion                                 | Virtual network                                                                                                                              | bas-{účel/služba/aplikácia/projekt}-{prostredie}-{region}-{###}                                                                                        | bas-itam-prod-northeu-001                    |
| DNS private zone custom                 | Resource group                                                                                                                               | {doména}.sk                                                                                                                                            | itam.sk                                     |
| DNS private zone central                | Resource group                                                                                                                               | [https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-dns](https://learn.microsoft.com/en-us/azure/private-link/private-endpoint-dns) | privatelink.database.windows.net            |
| DNS private link                        | Resource group                                                                                                                               | dnslink-{názov vnety}                                                                                                                                  | dnslink-kav-mirri-dev-northeu               |

#### Virtual Machines
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Virtual Machine                         | Resource group                                                                                                                               | vcm-{služba/aplikácia/projekt}-{prostredie}-{region}-[špecifikácia]-{###}                                                                              | vcm-itam-prod-northeu-sql-001                |
| VM Scale Set                            | Resource group                                                                                                                               | vmss-{meno setu pre vm}                                                                                                                                | vmss-vcm-itam-prod-northeu-sql               |
| VM Availability Set                     | Resource group                                                                                                                               | vmas-{služba/aplikácia/projekt}-{špecifikácia}-{prostredie}                                                                                            | vmas-itam-sql-prod                          |
| Manage Disks                            | Resource group                                                                                                                               | disk-{služba/aplikácia/projekt}-{prostredie}-{region}-[špecifikácia]-{###}                                                                             | disk-itam-prod-northeu-sql-db-001            |
| VM Storage account                      | Global                                                                                                                                       | sta-{služba/aplikácia}-{prostredie}{###}                                                                                                               | sta-itam-prod-001                           |
| DNS Label                               | Global                                                                                                                                       | {A record of vm}.[{region}.cloudapp.azure.com]                                                                                                         | web1.eastus2.cloudapp.azure.com             |
| Load Balancer                           | Resource group                                                                                                                               | lb-{služba/aplikácia}-{prostredie}-{region}-[špecifikácia]{###}                                                                                        | lb-itam-prod-northeu-sql-001                 |
| NIC                                     | Resource group                                                                                                                               | nic-{##}-{vmname}-{prostredie}-{region}-[špecifikácia]{###}                                                                                            | nic-01-vcm-itam-nonprod-northeu-inv-001      |

#### Kubernetes Services AKS

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| AKS Cluster                             | Resource group                                                                                                                               | aks-{vnet}-{meno aks clustra}-{prostredie}-{region}-{###}                                                                                              | aks-mirri-prod-northeu-001                   |
| Container Instances                     | Resource group                                                                                                                               | ci-{meno aks clustra}-{###}                                                                                                                            | ci-mirri-001                                |
| Container Registry                      | Resource group                                                                                                                               | cr-{vnet}-{meno aks clustra}{###}                                                                                                                      | cr-mirri-001                                |

#### VMware Services SDDC    

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| VMware Services SDDC                    | Global                                                                                                                                       | sddc-{meno vCenter}-{region}                                                                                                                           | sddc-vcmirri-northeu                         |

#### Storage       

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Azure Storage account - general use     | Global                                                                                                                                       | stg{služba/aplikácia/projekt}{###}                                                                                                                     | stgkav001                                   |
| Azure Storage account - diagnostic logs | Global                                                                                                                                       | stdiag{služba/aplikácia/projekt}{region}{###}                                                                                                         | stdiagkavnortheu001                         |

#### Security

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Key Vault                               | Resource group                                                                                                                               | keyv-{služba/aplikácia/projekt}-{prostredie}{###}                                                                                                      | keyv-kav-prod-001                           |
| HSM                                     | Resource group                                                                                                                               | hsm-{OVM}                                                                                                                                              | hsm-mirrisr                                 |                  |                                                                                                       
| Managed identity                        | Resource group                                                                                                                               | id-{služba/aplikácia/projekt}-{prostredie}-{###}                                                                                                       | id-kav-prod-001                             |
| Terraform identity                      | Managed identity                                                                                                                             | svc-trf-{služba/aplikácia/projekt}-{prostredie}                                                                                                        | svc-trf-metais-prod                         |

#### PaaS Services         

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| App Service                             | Global                                                                                                                                       | azapp-{služba/aplikácia}-{prostredie}{###}.[{azurewebsites.net}]                                                                                       | azapp-navigator-prod-001.azurewebsites.net  |
| Function App                            | Global                                                                                                                                       | azfun-{služba/aplikácia}-{prostredie}{###}.[{azurewebsites.net}]                                                                                       | azfun-navigator-prod-001.azurewebsites.net  |
| Cloud Services                          | Global                                                                                                                                       | azcs-{služba/aplikácia}-{prostredie}{###}.[{cloudapp.net}]                                                                                             | azcs-navigator-prod-001.azurewebsites.net   |

#### Service Bus        

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Service Bus                             | Global                                                                                                                                       | sb-{služba/aplikácia}-{prostredie}{###}.[{servicebus.windows.net}]                                                                                     | sb-navigator-prod                           |
| Service Bus queues                      | Service Bus                                                                                                                                  | sbq-{popis dopytu}                                                                                                                                     | sbq-messagequery                            |

#### AI + Machine Learning        

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Azure Search                            | Global                                                                                                                                       | srch-{služba/aplikácia}-{prostredie}                                                                                                                   | srch-navigator-prod                         |
| Cognitive Services                      | Resource group                                                                                                                               | cs-{služba/aplikácia}-{prostredie}                                                                                                                     | cs-navigator-prod                           |
| ChatGPT                                 | Resource group                                                                                                                               | chatgpt-{služba/aplikácia/projekt}-[OR]-{prostredie}-{region}                                                                                          | chatgpt-metais-prod-northeu                  |
| Azure Machine Learning workspace        | Resource group                                                                                                                               | aml-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                     | aml-navigator-prod-northeu                   |

#### Analytics    

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Azure Log Analytics Workspace                      | Global                                                                                                                                       | law-{služba/aplikácia/projekt}-{OR}-{prostredie}-{region}-{###}                                                                                        | law-kav-mirri-prod-northeu-001               |
| Azure Data Factory                      | Global                                                                                                                                       | adf-{služba/aplikácia/projekt}-{OR}-{prostredie}-{region}-{###}                                                                                        | adf-kav-mirri-prod-northeu-001               |
| Azure Data Lake Storage                 | Global                                                                                                                                       | dls{služba/aplikácia/projekt/OR}{###}                                                                                                                  | dlskavmirriprod001                          |
| Azure Data Bricks                       | Global                                                                                                                                       | dbx-{služba/aplikácia/projekt}-{OR}-{prostredie}-{region}-{###}                                                                                        | dbx-kav-mirri-prod-northeu-001               |
| Azure Data Lake Analytics               | Global                                                                                                                                       | dla{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                      | dlakavmirriprod-northeu-001                  |
| Power BI Embedded                       | Global                                                                                                                                       | pbiemb-{služba/aplikácia/projekt}-{OR}-{prostredie}-{region}-{###}                                                                                     | pbiem-kav-mirri-prod-northeu-001             |
| HDInsight - Spark                       | Global                                                                                                                                       | hdis-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                    | hdis-navigator-prod-northeu-001              |
| HDInsight - Hadoop                      | Global                                                                                                                                       | hdihd-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                   | hdihd-hadoop-prod-northeu-001                |
| HDInsight - R server                    | Global                                                                                                                                       | hdir-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                    | hdir-navigator-prod-northeu-001              |
| HDInsight - HBase                       | Global                                                                                                                                       | hdihb-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                   | hdihb-navigator-prod-northeu-001             |

#### Internet of Things         

|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Event Hub                               | Resource group                                                                                                                               | evh-queue-{prostredie}-{topic}-{text format}                                                                                                           | evh-queue-egov-form-json                    |
| Event Hub Namespace                     | Resource group                                                                                                                               | evhns-{služba/aplikácia/OR}-{prostredie}-{region}-{###}                                                                                                | evhns-metais-shared-northeu-001             |
| Notification Hub                        | Resource group                                                                                                                               | anh-{služba/aplikácia/OR}-{prostredie}-{region}-{###}                                                                                                  | anh-mirri-shared-northeu-001                |
| Notification Hub Namespace              | Global                                                                                                                                       | anhns-{služba/aplikácia/OR}-{prostredie}-{region}-{###}                                                                                                | anhns-mirri-shared-northeu-001              |
| Azure Stream Analytics on IoT Edge      | Resource group                                                                                                                               | asa-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                     | asa-navigator-prod-northeu-001               |
| Azure IoT Hub                           | Global                                                                                                                                       | aih-{služba/aplikácia}-{prostredie}-{region}-{###}                                                                                                     | aih-navigator-prod-northeu-001               |

### Konvencia pomenovania OR časti

Inštrukcie: Tento hárok použite na definovanie štandardov pomenovávania, ktoré chcete použiť na každý typ prostriedku, ktorý plánujete nasadiť.

#### Virtual Networking Spoke
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
| Virtual Network Spoke                   | Resource group                                                                                                                               | vnet-{služba/aplikácia/projekt}-{prostredie}-{region}                                                                                                  | vnet-itam-prod-northeu                       |
| Subnet                                  | Virtual network                                                                                                                              | snet-{projekt}-{prostredie}-{účel/služba/aplikácia}                                                                                                    | snet-itam-prod-sql                          |
| Azure Virtual Desktop                   | Virtual network                                                                                                                              | avd-{účel/služba/aplikácia/projekt}-{prostredie}-{region}-{###}                                                                                        | avd-itam-prod-northeu-001                    |
| Bastion                                 | Virtual network                                                                                                                              | bas-{účel/služba/aplikácia/projekt}-{prostredie}-{region}-{###}                                                                                        | bas-itam-prod-northeu-001                    |

