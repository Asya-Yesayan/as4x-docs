---
layout: page
title: JOBEXECUTION աղյուսակ
---

Այս աղյուսակը նախատեսված է կատարման ընթացքում գտնվող/ավարտված առաջադրանքների (job) ինֆորմացիայի պահպանման համար։

| Սյան անվանում | Տվյալների տիպ | Null | Նկարագրություն |
| --- | --- | --- | --- |
 | fEXECUTIONID	 |   int	            | not null  | Առաջադրանքի id-ն։         |
| fJOBISN	     |   int	            | not null  | Առաջադրանքի ձևանմուշը նկարագրող փաստաթղթի ներքին նույնականացման համարը (isn):          |
| fJOBCODE	     |   varchar(32)	    | not null  | Առաջադրանքի կոդը։          |
| fTARGETSERVICE |	varchar(32)	        | not null  | Այն վեբ ծառայության (սերվիսի) id-ն, որի վրա գործարկվել է տվյալ առաջադրանքը։ <br> Վեբ ծառայությունները սահմանվում են «Ադմինիստրատորի աշտ» -> «Համակարգային աշխատանքներ» -> **«8X Web ծառայություններ»** հաշվետվության **Ավելացնել** կոնտեքստային ֆունկցիայով։ <br> Սահմանվող վեբ ծառայության դերը անհրաժեշտ է նշել **JobExecuter**՝ ծառայության միջոցով առաջադրանքների գործարկումը թույլատրելու նպատակով:         |
| fSUID	         |   smallint	        | null      | Առաջադրանքը կատարած օգտագործողի կոդը։          |
| fACTIVATION	 |   tinyint	        | not null  | Առաջադրանքի գործարկման տեսակը։ <br> **0** - Ձեռքով, <br> **1** - ժամանակացույց, <br> **2** - Առաջադրանքից հետո, <br> **3** - Իրադարձությունից հետո։          |
| fBEGINDATE	 |   datetime	        | not null  | Առաջադրանքի կատարման սկզբի ամսաթիվը/ժամանակը։          |
| fENDDATE	     |   datetime	        | null      | Առաջադրանքի կատարման ավարտի ամսաթիվը/ժամանակը։          |
| fJOBDATE	     |   smalldatetime	    | null      | Առաջադրանքի կատարման ամսաթիվը։          |
| fSTATE	     |   tinyint	        | not null  | Ավարտված առաջադրանքի վիճակը։ <br> **1** - Կատարման ընթացքում, <br> **2** - Բարեհաջող կատարված,  <br> **3** - Ընդհատված կատարում։         |
| fCOMMENT	     |   nvarchar(255)	    | not null  | Առաջադրանքի կատարման մեկնաբանությունը։         |
| fHASERROR	     |   bit	            | null      | Առաջադրանքի կատարման ընթացքում սխալների առաջացման հայտանիշ։          |

**Օրինակ**

| fEXECUTIONID | fJOBISN | fJOBCODE | fTARGETSERVICE | fSUID | fACTIVATION | fBEGINDATE | fENDDATE | fJOBDATE | fSTATE | fCOMMENT | fHASERROR |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 3 | 288355629 | JobTest | dbank6 | 10 | 0 | 2025-10-15 11:43:54.250 | 2025-10-15 11:44:31.620 | 2025-10-15 00:00:00 | 2 | Job execution completed successfully | 0 |

## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| PK_fEXECUTIONID | Unique, Clustered   | fEXECUTIONID     |
| iJOBEXECUTION1  | NonClustered        | fJOBCODE, fBEGINDATE     |
| iJOBEXECUTION2  | NonClustered        | fBEGINDATE, fJOBCODE     |





