## Konvencia pomenovania Taggov

Tento hárok použite na definovanie značiek metadát, ktoré chcete použiť na zdroje. 

|Tag name |Description |Key |Example Values |Required |
| - | - | - | - | - |
|DataClassification |Klasifikácia citlivosti dát / NBU |Classification |Verejne, Dôverne, Tajne, Prísne Tajne |Yes |
|Criticality |Kritickosť služby/aplikácie vychádzajúca z SLA |Criticality |Nízka, Stredná, Vysoká, Kritická |Yes |
|OrgRiadenia |Organ verejnej moci |Org |MVSR, NASES, MIRRISR |Yes |
|ProjectName |Názov projektu pod ktorým sú služby/aplikácie dodávane |Project Name |Metais_XXXX - costcenter |Yes |
|OpsTeam |Názov IT ops teamu podľa organizačnej štruktúry |Operations |CloudTeam |Yes |
|Environment |Prostredie kde služba/aplikácia beží |Subscription |Prod, NonProd |Yes |
|Owner |e-mail osoby zodpovednej za službu/aplikáciu |Stakeholder |meno@mirri.gov.sk |Yes |
|Start projektu |Dátum začiatku určuje časovú os projektu |StartDate |{dd.mm.yyyy} |Yes |
|MetaIS |Identifikátor ISVS |Kód ISVS |projekt_XXXX |Yes |
|Koniec projektu |Dátum konca určuje časovú os projektu |EndDate |{dd.mm.yyyy} |Yes |
|Runtime |Automatické vypínanie/zapínanie resources pomocou tags den/noc/vikend/sviatok |"StartTime EndTime" |"Start [06:00][Day] End [17:00][Day]" |No |


