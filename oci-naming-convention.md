## Syntax Mennej Konvencie pre verejnú časť vládneho cloudu / Oracle Cloud Infrastructure (OCI) 

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

#### Network komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|Virtual Cloud Network | VCN |
|Subnet | SBN  |
|Routovacia Tabulka | VRT |
|Internetova Gateway | IGW |
|NAT Gateway | NAT |
|Network Security Group | NSG |
|Security List | SEL  |
|DHCP Options | DHO |
|Local Peering Gateway | LPG |
|Service Gateway | SEG |
|Attachment | ATC |
|Web Application Firewall | WAF |
|Network Load Balancer | NLB |
|DNS Management  | DNS |
|Site-to-Site IPSEC VPN | VPN |
|Fast Connect | FCN |
|Dynamic Routing Gateway | DRG |
|Customer-Premises Equipment | CPE |
|Reserved Public IPs | PIP |
|Bring Your Own IP/s | BYI |
|Public IP Pools | PPO |
|Network Path Analyzer | NPA |
|VLANs (Pouzivane iba pri ESXi vmWare ) | VLN |

#### Compute komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|Work Request | WRQ |
|Virtual Compute Instance  | VCM |
|Dedikovany Bare Metal Host  | BMH |
|Virtual Compute Konfiguracia | VCC |
|Pool Virtual Compute Nodov | VCP |
|Compute Cluster Network | CCN |
|Compute Auto-Scaling Configuration | ASC |
|Compute Capacity Reservation | CCR |
|Compute Custom Image | CCI |
|Compute Instance Network Interface Card | NIC |
|Compute Custom Command | CCC |
|Compute Work Request | CWR |

#### Storage komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|Storage Block Volume | SBV |
|Storage Volume Group| SVG |
|Storage Backup Policy | SBP |

#### Database komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|DB Channels | DCH |
|DB Systems| DBS |
|DB Configurations | DCF |

#### Oracle Databazy komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|Autonomous Container Database | ACD |
|Autonomous Exadata VM Cluster | AEC |
|Exadata Infrastructure| EIN |
 
#### Identity komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|Identity User Policy | IUP |
 
#### Security komponenty
|Popis OCI Komponentov |Skratka |
--- | --- |
|Key Vault | KEY |
|HSM | Hardware Security Module | 

### Špecifikácia OR

V tejto časti špecifikujeme možné povinné polia pri názve OR-ky. V prípade ak nastane aktualizácia údajov v tabuľke (názov, skratka, alebo pridanie či odstránenie záznamu), je povinnosťou vzhliadajúceho tento údaj príslušne upraviť a to tak aby reflektoval na aktuálnu situáciu. 

#### Skratka OR
|Cely názov OR |Skratka |
--- | --- |
|Datacentrum elektronizácie územnej samosprávy Slovenska | DEUS |
|Dôvera - zdravotná poisťovňa | DOVERAZP |
|Exportno-importná banka SR | EXIMBANKA |
|Generálna prokuratúra SR | GPSR |
|Kancelária Najvyššieho súdu SR | NSUD |
|Kancelária Národnej rady SR | NRSR |
|Kancelária prezidenta SR | PREZIDENT |
|Kancelária Súdnej rady SR | SUDNARADA |
|Kancelária Ústavného súdu SR | USTAVNYSUD |
|Kancelária verejného ochrancu práv | VOP |
|Ministerstvo dopravy a výstavby SR | MINDOP |
|Ministerstvo financií SR | MFSR |
|Ministerstvo hospodárstva SR | MHSR |
|Ministerstvo investícií, regionálneho rozvoja a informatizácie SR | MIRRI |
|Ministerstvo kultúry SR| MKSR |
|Ministerstvo obrany SR| MOSR |
|Ministerstvo pôdohospodárstva a rozvoja vidieka SR| MPSR |
|Ministerstvo práce, sociálnych vecí a rodiny SR | MPSVR |
|Ministerstvo spravodlivosti SR | JUSTICE |
|Ministerstvo školstva, vedy, výskumu a športu SR | MINEDU |
|Ministerstvo vnútra SR | MVSR |
|Ministerstvo školstva, vedy, výskumu a športu SR | MZSR |
|Ministerstvo zahraničných vecí a európskych záležitostí SR | MINEDU |
|Ministerstvo zahraničných vecí a európskych záležitostí SR | MZSR |
|Ministerstvo zdravotníctva SR | MZSR |
|Ministerstvo životného prostredia SR | MINZP |
|Najvyšší kontrolný úrad SR | NKU |
|Národný bezpečnostný úrad | NBU |
|Protimonopolný úrad SR | ANTIMON |
|Rada pre vysielanie a retransmisiu SR | RVR |
|Rozhlas a televízia Slovenska | RTVS |
|Slovenská lekárska komora | SLK |
|Sociálna poisťovňa | SP |
|Správa štátnych hmotných rezerv SR | RESERVES |
|Štatistický úrad SR | SUSR |
|Tlačová agentúra SR | TASR |
|Union - zdravotná poisťovňa | UNIONZP |
|Úrad geodézie, kartografie a katastra SR | UGKK |
|Úrad jadrového dozoru SR | UJD |
|Úrad komisára pre deti | UKPD |
|Úrad komisára pre osoby so zdravotným postihnutím | UKPOZP |
|Úrad na ochranu osobných údajov | UOOU |
|Úrad pre dohľad nad zdravotnou starostlivosťou | UDZS |
|Úrad pre normalizáciu, metrológiu a skúšobníctvo SR | UNMS |
|Úrad pre reguláciu elektronických komunikácií a poštových služieb | UREKPS |
|Úrad pre normalizáciu, metrológiu a skúšobníctvo SR | UNMS |
|Úrad pre reguláciu sieťových odvetví SR | URSO |
|Úrad pre verejné obstarávanie | UVO |
|Úrad priemyselného vlastníctva SR | UPV |
|Úrad vlády SR  | UVSR |
|Ústav pamäti národa | UPNSR |
|ÚVšeobecná zdravotná poisťovňa | VSZP |

### Syntax mennej konvencie v OCI 

