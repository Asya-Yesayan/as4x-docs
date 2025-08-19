---
layout: page
title: REPORTCALLS աղյուսակ
---

Այս աղյուսակը նախատեսված է օգտագործողի կողմից կանչվող դիտելու ձևերի վիճակագրության հավաքագրման համար։

| Սյան անվանում | Տվյալների տիպ | Null | Նկարագրություն |
| --- | --- | --- | --- |
| fREPCALLID | uniqueidentifier | null | Գրանցվող գրառման ներքին նույնականացման համարը (Guid), որը գեներացվում է ավտոմատ կերպով։ |
| fUSERID | smallint | not null | Դիտելու ձևը կանչող օգտագործողի ներքին համարը (կոդ)։ |
| fCOMPNAME | varchar(32) | not null | Դիտելու ձևը կանչող կայանի անունը։ |
| fSESSIONID | uniqueidentifier | not null | Այն սեսսիայի ներքին նույնականացման համարը (Guid), որի շրջանակներում կանչվել է դիտելու ձևը։ |
| fDATE | datetime | not null | Դիտելու ձևի կանչի ամսաթիվը/ժամանակը։ |
| fBASEVIEW | char(8) | not null | Հիմքային դիտելու ձևի ներքին անունը։ |
| fVIEWNAME | varchar(50) | not null | Դիտելու ձևի ներքին անունը։ |
| fDATASOURCENAME | char(8) | not null | Դիտելու ձևի հիմքային տվյալների աղբյուրի ներքին անունը։ |
| fDURATION | int | not null | Դիտելու ձևի կատարման տևողությունը վայրկյաններով։ |
| fROWCOUNT | int | not null | Դիտելու ձևի տողերի քանակը։ |
| fCANCELLED | bit | not null | UI-ից կատարման ընդհատման հայտանիշ։ |
| fAPICLIENTID | smallint | not null | Այն կլիենտ ծրագրի ներքին նույնականացման համարը (id), որի շրջանակներում կանչվել է դիտելու ձևը։ |

## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| iREPORTCALLS1 | Unique, Clustered | fREPCALLID |
| iREPORTCALLS2 | | fDATE |
