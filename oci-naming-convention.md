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
Meno objektu musí mať počet znakov medzi 1-254 
Meno objektu môže obsahovať akékoľvek špeciálne znaky, veľké aj malé písmena, čísla a aj interpunkčné znamienka slovenskej abecedy. 

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

V tejto časti bližšie špecifikujeme skratky, ktoré používame v kapitole 4. 

 

Skratky OCI Komponentov 

Network 

VCN 

Virtual Cloud Network 

SBN 

Subnet / Pod VCNkom 

VRT 

Routovacia Tabulka / Pod VCNkom 

IGW 

Internetova Gateway / Pod VCNkom 

NAT 

NAT Gateway / Pod VCNkom 

NSG 

Network Security Group / Pod VCNkom 

SEL 

Security List / Pod VCNkom 

DHO 

DHCP Options / Pod VCNkom 

LPG 

Local Peering Gateway / Pod VCNkom 

SEG 

Service Gateway / Pod VCNkom 

ATC 

Attachment 

WAF 

Web Application Firewall 

LBL 

Load Balancer 

NLB 

Network Load Balancer 

DNS 

DNS Management 

VPN 

Site-to-Site VPN 

FCN 

Fast Connect 

DRG 

Dynamic Routing Gateway 

CPE 

Customer-Premises Equipment 

PIP 

Reserved Public IPs 

BYI 

Bring Your Own IP/s 

PPO 

Public IP Pools 

NPA 

Network Path Analyzer 

DHO 

DHCP Options 

VLN 

VLANs / Pouzivane iba pri ESXi vmWare 

 

 

Compute 

WRQ 

Work Request 

VCM 

Virtual Compute Instance 

BMH 

Dedikovany Bare Metal Host 

VCC 

Virtual Compute Konfiguracia 

VCP 

Pool Virtual Compute Nodov 

CCN 

Compute Cluster Network 

ASC 

Compute Auto-Scaling Configuration 

CCR 

Compute Capacity Reservation 

CCI 

Compute Custom Image 

NIC 

Compute Instance Network Interface Card 

CCC 

Compute Custom Command 

CWR 

Compute Work Request 

 

 

Storage 

SBV 

Storage Block Volume 

SVG 

Storage Volume Group 

SBP 

Storage Backup Policy 

 

 

Database 

DBS 

DB Systems 

DCH 

DB Channels 

DCF 

DB Configurations 

Oracle Database 

ACD 

Autonomous Container Database 

AEC 

Autonomous Exadata VM Cluster 

EIN 

Exadata Infrastructure 

 

 

Identity 

IUP 

Identity User Policy 

 

Security 

KEY 

Key Vault 

HSM 

HSM  

### Syntax mennej konvencie v OCI 

Špecifikácia ORiek 

V tejto časti špecifikujeme možné povinné polia pri názve OR-ky. V prípade ak nastane aktualizácia údajov v tabuľke (názov, skratka, alebo pridanie či odstránenie záznamu), je povinnosťou vzhliadajúceho tento údaj príslušne upraviť a to tak aby reflektoval na aktuálnu situáciu. 

 

Skratka OR-ky 

Cely názov OR-ky 

DEUS 

Datacentrum elektronizácie územnej samosprávy Slovenska 

DOVERAZP 

Dôvera - zdravotná poisťovňa  

EXIMBANKA 

Exportno-importná banka SR  

GPSR 

Generálna prokuratúra SR  

NSUD 

Kancelária Najvyššieho súdu SR  

NRSR 

Kancelária Národnej rady SR  

PREZIDENT 

Kancelária prezidenta SR  

SUDNARADA 

Kancelária Súdnej rady SR  

USTAVNYSUD 

Kancelária Ústavného súdu SR  

VOP 

Kancelária verejného ochrancu práv  

MINDOP 

Ministerstvo dopravy a výstavby SR  

MFSR 

Ministerstvo financií SR  

MHSR 

Ministerstvo hospodárstva SR  

MIRRI 

Ministerstvo investícií, regionálneho rozvoja a informatizácie SR  

MKSR 

Ministerstvo kultúry SR  

MOSR 

Ministerstvo obrany SR  

MPSR 

Ministerstvo pôdohospodárstva a rozvoja vidieka SR  

MPSVR 

Ministerstvo práce, sociálnych vecí a rodiny SR  

JUSTICE 

Ministerstvo spravodlivosti SR  

MINEDU 

Ministerstvo školstva, vedy, výskumu a športu SR  

MVSR 

Ministerstvo vnútra SR  

MZSR 

Ministerstvo zahraničných vecí a európskych záležitostí SR  

MZSR 

Ministerstvo zdravotníctva SR  

MINZP 

Ministerstvo životného prostredia SR  

NKU 

Najvyšší kontrolný úrad SR  

NBU 

Národný bezpečnostný úrad   

ANTIMON 

Protimonopolný úrad SR  

RVR 

Rada pre vysielanie a retransmisiu SR  

RTVS 

Rozhlas a televízia Slovenska  

SLK 

Slovenská lekárska komora  

SP 

Sociálna poisťovňa  

RESERVES 

Správa štátnych hmotných rezerv SR  

SUSR 

Štatistický úrad SR  

TASR 

Tlačová agentúra SR  

UNIONZP 

Union - zdravotná poisťovňa  

UGKK 

Úrad geodézie, kartografie a katastra SR  

UJD 

Úrad jadrového dozoru SR  

UKPD 

Úrad komisára pre deti  

UKPOZP 

Úrad komisára pre osoby so zdravotným postihnutím  

UOOU 

Úrad na ochranu osobných údajov  

UDZS 

Úrad pre dohľad nad zdravotnou starostlivosťou   

UNMS 

Úrad pre normalizáciu, metrológiu a skúšobníctvo SR  

UREKPS 

Úrad pre reguláciu elektronických komunikácií a poštových služieb  

URSO 

Úrad pre reguláciu sieťových odvetví SR  

UVO 

Úrad pre verejné obstarávanie  

UPV 

Úrad priemyselného vlastníctva SR  

UVSR 

Úrad vlády SR  

UPNSR 

Ústav pamäti národa  

VSZP 

Všeobecná zdravotná poisťovňa  

