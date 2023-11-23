## Syntax Mennej Konvencie pre verejnú časť vládneho cloudu / Oracle Cloud Infrastructure (OCI) 
- [Obsah Dokumentu](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#obsah-dokumentu)
- [Ucel Dokumentu](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#%C3%BA%C4%8Del-dokumentu)
- [Cielove Publikum](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#cie%C4%BEov%C3%A9-publikum)
- [Pouzite Skratky](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#pou%C5%BEit%C3%A9-skratky)
- [Zname limitacie v menach objektov](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#zn%C3%A1me-limit%C3%A1cie-vmen%C3%A1ch-objektov)
- [Odporucania k mennej konvencii](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#odpor%C3%BA%C4%8Dania-kmennej-konvencii)
- [Skratky OR a prostredi](https://github.com/slovak-egov/vladny-cloud/blob/main/or-naming-convention)
- [Syntax Mennej Konvencie v OCI](https://github.com/slovak-egov/vladny-cloud/blob/main/oci-naming-convention.md#syntax-mennej-konvencie-v-oci)

### Obsah dokumentu

Tento dokument presne popisuje pravidlá pomenovávania objektov v Oracle Cloud Infraštruktúre. 

### Účel dokumentu 

Účelom tohto dokumentu je nastaviť jednoduché a jasne pravidla pre všetkých čo budú Oracle Cloud Infraštruktúru používať. 
Jedine pri presne nastavenej mennej konvencii je v budúcnosti možné jednoduché vytváranie automatizovaných objektov. Ak by sme tieto pravidla nemali, automat by musel mat pri vstupe veľa podmienok pre vstupno-výstupné validácie. 

### Cieľové publikum 

Užívatelia nastavujúci alebo využívajúci služby Oracle Cloud Infraštruktúry.  
Architekti, ktorí budú využívať tieto pravidla ďalej pri automatizácii a zároveň ich budú vynucovať od užívateľov. 

### Použité skratky 

V tomto dokumente budú na účely vysvetlenia pravidiel používané tieto skratky : 

|Cely názov |Skratka |
--- | --- |
|Oracle Cloud Infrastructure |OCI |
|Orgán Riadenia | OR |
|Internet Private Line (Internetové pripojenie)  | IPL  |
|Ethernet Private Line (Privátne pripojenie)  | EPL |

### Známe limitácie v menách objektov 

Menná konvencia musí vychádzať z limitácii objektov, aby sme mohli stanoviť presné pravidlá a predišli problémom s príliš dlhým menom objektu, ktorý nebude možný. V nasledujúcich odstavcoch popisujem presné limitácie mien objektov, ktoré treba brať do úvahy. 

Najzakladanejšiu limitáciu v menných konvenciách vo väčšine prípadov predstavuje parameter hostname, ktorý je vo väčšine prípadov (prienik medzi Linuxom, využívajúcim hostnamectl a Windows) 63 znakov, ktoré pozostávajú so znakov A-Z, a-z, 0-9 a špeciálneho znaku – pomlčky, ktorou ale začínať nesmie. 
Pri menách „compute“ objektov, sa tieto objekty priamo premietajú do hostname parametra, no v prípade ak meno objektu presiahne 63 znakov, zvyšnú časť po 63. znaku do parametra hostname nedá. 
Ďalšou dôležitou limitáciou, ktorú treba brať do úvahy, pri navrhovaní mennej konvencie je DNS meno, ktoré je síce dosť dlhé (255 možných znakov) ale tiež môže využívať len znaky popísane v hostname časti a bodku, ktorou ale začínať nemôže. V tejto časti je dôležité zdôrazniť, že sa počítajú aj znaky použite v hlavnej doméne, všetkých subdoménach a aj všetky oddeľovacie bodky. 

V neposlednom rade musíme počítať aj s limitáciami samotného OCI, ktoré sú pre jednotlivé komponenty definované takto :  
- Meno objektu musí mať počet znakov medzi 1-254 
- Meno objektu môže obsahovať akékoľvek špeciálne znaky, veľké aj malé písmena, čísla a aj interpunkčné znamienka slovenskej abecedy. 

### Odporúčania k mennej konvencii 

Menná konvencia musí byt :  
- Jednoduchá – pravidla nesmú obsahovať veľa podmienok ci výnimiek 
- Ľahko pochopiteľná – tabuľka s pravidlami musí byt jasná pre pochopenie. 

Vymožiteľná politikou ci auditmi – v prípade ak je to možné v politike, sme povinní si vymôcť jej používanie. Ak nie, tak pri vylistovaní existujúcich objektov môžeme správcu OR upozorniť na jej porušenie a vyžiadať nápravu. 

Menná konvencia musí byť rozdelená na : 

- Fixnú (centrálnu) časť, ktorá bude reprezentovať objekty v Hub-och. V nej musia byt pravidlá čo možno najprísnejšie, aby bolo jednoduché vypočítať meno ďalšieho objektu automatizáciou. 
- Variabilnú (OR) časť, ktorá bude reprezentovať objekty v Spoke-och. V tejto časti musí byť fixná len úvodná časť (prefix) mena objektu a zvyšok necháme na správcovi OR-ky. 

Menná konvencia by nemala používať interpunkčné znamienka, aby nedošlo k nepredvídateľným problémom s automatizáciou. 
Menná konvencia musí zakázať používanie špeciálnych znakov, ktoré sú definované ako XSS (Cross-Site Scripting) znaky. Sú to tieto : <, >, (,), #, ', " a medzera. 
Na jednoznačnú identifikáciu regiónu v OCI je potrebné použiť trojznakové označenie podľa ISO 3166-1 : 

- Pre verejné regióny definované na OCI dokumentácií 
- Pre privátne regióny definované ako skratka Slovenského mesta podľa ISO štandardu

Výsledné odporúčanie je na základe limitácií v menách objektov, by menná konvencia nemala umožňovať meno dlhšie ako 63 znakov, obsahujúce veľké a malé znaku abecedy, čísla a pomlčku. 

### Špecifikácie objektov v OCI 

V tejto časti bližšie špecifikujeme skratky, ktoré používame v nasledujúcej kapitole.

### Špecifikácia OR

V dedikovanom dokumente, pretoze je to spolocna cast pre vsetky naming convention dokumenty. Mozete to najst tu : [Skratky OR a prostredi](https://github.com/slovak-egov/vladny-cloud/blob/main/or-naming-convention)

### Syntax mennej konvencie v OCI 

Táto časť slúži na definovanie štandardov pomenovávania, ktoré chcete použiť na každý typ prostriedku, ktorý plánujete nasadiť.

#### Compartment
|Typ Assetu |OR |Formát |Príklad |
--- | --- | --- | --- |
|cmp |Account OR |mgmt-(OR)-(prostredie) |cmp-mirri-prod, cmp-mirri-nonprod |

#### Subskripcie
|Typ Assetu |OR |Formát |Príklad |
--- | --- | --- | --- |
|sub |Account/Enterprise Agreement |sub-(služba/aplikácia/projekt)-(prostredie)-(###) |sub-itam-prod-001 |

#### Sieťové komponenty
|Typ Assetu |Popis |Formát |Príklad |
--- | --- | --- | --- |
VCN	|Virtual Cloud Network |vcn-(hub/dmz/OR)-(gov/nogov)-(prod/test/dev/shared)-(region) |vcn-hub-gov-prod-eu-frankfurt-1 |
SNET	|Subnet |snet-(účel/služba/aplikácia)-(prostredie)-(region)-(###) |snet-shared-prod-westeu-001 |
VRT	|Routovacia Tabulka | | |
IGW	|Internetova Gateway | | |
NAT	|NAT Gateway | | |
NSG	|Network Security Group | | |
SEL	|Security List | | |
DHO	|DHCP Options | | |
LPG	|Local Peering Gateway | | |
SEG	|Service Gateway | | |
ATC	|Attachment | | |
WAF	|Web Application Firewall | | |
LBL	|Load Balancer | | |
NLB	|Network Load Balancer | | |
DNS	|DNS Management | | |
VPN	|Site-to-Site VPN | | |
FCN	|Fast Connect | | |
DRG	|Dynamic Routing Gateway | | |
CPE	|Customer-Premises Equipment | | |
PIP	|Reserved Public IPs | | |
BYI	|Bring Your Own IP/s | | |
PPO	|Public IP Pools | | |
NPA	|Network Path Analyzer | | |
DHO	|DHCP Options | | |
VLN	|VLANs / Pouzivane iba pri ESXi VMware | | |

#### VM komponenty
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
WRQ	|Work Request | | |
VCM	|Virtual Compute Instance | | |
BMH	|Dedikovany Bare Metal Host | | |
VCC	|Virtual Compute Konfiguracia | | |
VCP	|Pool Virtual Compute Nodov | | |
CCN	|Compute Cluster Network | | |
ASC	|Compute Auto-Scaling Configuration | | |
CCR	|Compute Capacity Reservation | | |
CCI	|Compute Custom Image | | |
NIC	|Compute Instance Network Interface Card | | |
CCC	|Compute Custom Command | | |
CWR	|Compute Work Request | | |

#### Kubernetes komponenty
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |

#### Storage komponenty
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
SBV	|Storage Block Volume | | |
SVG	|Storage Volume Group | | |
SBP	|Storage Backup Policy | | |

#### Database komponenty
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
DBS	|DB Systems | | |
DCH	|DB Channels | | |
DCF	|DB Configurations | | |
ACD	|Autonomous Container Database | | |
AEC	|Autonomous Exadata VM Cluster | | |
EIN	|Exadata Infrastructure | | |

#### Identity a Security komponenty
|Typ Assetu |Rozsah |Formát |Príklad |
--- | --- | --- | --- |
IUP	|Identity User Policy | | |
TNT	|Tenant | | |
KEY	|Key Vault | | |
HSM	|Hardware Security Module | | |





