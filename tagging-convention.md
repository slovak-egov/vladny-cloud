## Konvencia pomenovania Taggov

Tento hárok použite na definovanie značiek metadát, ktoré chcete použiť na zdroje. 

|Tag name |Description |Example Values |Required |
| - | - | - | - |
|DataClassification|Klasifikácia citlivosti dát / NBU |Verejne, Dôverne, Tajne, Prísne Tajne |Yes |
|Criticality|Kritickosť služby/aplikácie vychádzajúca z SLA |Nízka, Stredná, Vysoká, Kritická |Yes |
|OrgRiadenia|Organ verejnej moci |MVSR, NASES, MIRRISR |Yes |
|ProjectName|Názov projektu pod ktorým sú služby/aplikácie dodávane |Metais_XXXX - costcenter |Yes |
|OpsTeam|Názov IT ops teamu podľa organizačnej štruktúry |CloudTeam |Yes |
|Environment|Prostredie kde služba/aplikácia beží |Prod, NonProd |Yes |
|Owner|e-mail osoby zodpovednej za službu/aplikáciu |meno@mirri.gov.sk |Yes |
|StartDate|Dátum začiatku určuje časovú os projektu |{dd.mm.yyyy} |Yes |
|MetaIS|Identifikátor ISVS |Kód ISVS |Yes |
|EndDate|Dátum konca určuje časovú os projektu |{dd.mm.yyyy} |Yes |
|Runtime|Automatické vypínanie/zapínanie resources pomocou tags den/noc/vikend/sviatok |"Start [06:00][Day] End [17:00][Day]" |No |


