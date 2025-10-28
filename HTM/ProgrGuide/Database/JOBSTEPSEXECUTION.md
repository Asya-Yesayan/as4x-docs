---
layout: page
title: JOBSTEPSEXECUTION աղյուսակ
---

Այս աղյուսակը նախատեսված է առաջադրանքների ավարտված կատարման քայլերի (job) ինֆորմացիայի պահպանման համար։

| Սյան անվանում | Տվյալների տիպ | Null | Նկարագրություն |
| --- | --- | --- | --- |
| fEXECUTIONID	    |   int	            | not null  | Առաջադրանքի id-ն։      |
| fJOBCODE	        |   varchar(32)	    | not null  | Առաջադրանքի կոդը։      |
| fSTEP	            |   smallint	    | not null  | Կատարման քայլի համարը։     |
| fINTERRUPTONERROR	|   bit	not         | null      | Կատարման քայլում սխալ առաջանալու դեպքում առաջադրանքի ամբողջական ընդհատման հայտանիշ։      |
| fDPRNAME	        |   varchar(32)	    | not null  | Կատարման քայլում գործարկվող տվյալների մշակման հարցման (DPR) կոդը։      |
| fDPRTYPE	        |   char(2)	        | not null  | Կատարման քայլում գործարկվող տվյալների մշակման հարցման (DPR) տեսակի կոդը (OLAP - 22, JobElement - 23, ...): Լրացվում է ավտոմատ կերպով՝ **Առաջադրանքի ձևանմուշ** փաստաթղթի **Կատարման քայլեր** աղյուսակի **Գործողություն** դաշտը լրացնելիս:      |
| fPARAMS	        |   nvarchar(-1)    | not null  | Կատարման քայլում գործարկվող տվյալների մշակման հարցման (DPR) պարամետրերի անունների/արժեքները պարունակող json օբյեկտ։      |
| fBEGINDATE	    |   datetime	    | not null  | Կատարման քայլի սկզբի ամսաթիվը/ժամանակը։      |
| fENDDATE	        |   datetime	    | null      | Կատարման քայլի ավարտի ամսաթիվը/ժամանակը։      |
| fSTATE	        |   tinyint	        | not null  | Կատարման քայլի վիճակը։ <br> **2** - Բարեհաջող կատարված,  <br> **3** - Ընդհատված կատարում։      |
| fHASERROR	        |   bit	            | null      | Կատարման քայլի ընթացքում սխալների առաջացման հայտանիշ։      |

**Օրինակ**

| fEXECUTIONID | fJOBCODE | fSTEP | fINTERRUPTONERROR | fDPRNAME | fDPRTYPE | fPARAMS | fBEGINDATE | fENDDATE | fSTATE | fHASERROR |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 3 | JobTest | 1 | 0 | DPOCB18_1 | 22 | {"DateStart":"2025-10-15T00:00:00","DateEnd":"2025-10-15T00:00:00","ExportDaily":false} | 2025-10-15 11:43:54.280 | 2025-10-15 11:44:31.607 | 2 | 0 |


## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| PK_JOBSTEPSEXECUTION | Unique, Clustered  | fEXECUTIONID, fSTEP  |





