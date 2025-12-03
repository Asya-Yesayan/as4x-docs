---
layout: page
title: APPLOG աղյուսակ
---

Այս աղյուսակը նախատեսված է ծրագրային փոփոխությունների, իրադարձությունների (տարբերակի փոփոխություն, Debug-ի գործարկում, ․․․) պատմության պահպանման համար։

| Սյան անվանում | Տվյալների տիպ | Null | Նկարագրություն |
| --- | --- | --- | --- |
| fROWID | int | not null | Իրադարձության համարը։ Լրացվում է ավտոմատ կերպով։ |
| fDATE | datetime | not null | Իրադարձության իրականացման ամսաթիվը/ժամանակը։ |
| fSUID | smallint | not null | Իրադարձությունը իրականացրած օգտագործողի ներքին համարը (կոդը)։ |
| fMODCODE | char(4) | not null | Իրադարձության մոդուլի անունը։ |
| fOPERCODE | char(4) | not null | Իրադարձության կոդը։ |
| fCOMMENT | varchar(500) | not null | Իրադարձությունը նկարագրող մեկնաբանություն։ |
| fOBJISN | int | not null | Իրադարձությունը իրականացրած երկրորդային փաստաթղթի ներքին նույնականացման համար (isn)։ |
| fBASEISN | int | not null | Իրադարձությունը իրականացրած հիմքային փաստաթղթի ներքին նույնականացման համար (isn)։ |
| fCOMPNAME | varchar(32) | not null | Իրադարձությունը իրականացրած օգտագործողի համակարգչի անունը։ |
| fAPICLIENTID | smallint | not null | Այն կլիենտ ծրագրի ներքին նույնականացման համարը (id), որի շրջանակներում իրականացվել է իրադարձությունը։ |

**Օրինակ**

| fROWID | fDATE | fSUID | fMODCODE | fOPERCODE | fCOMMENT | fOBJISN | fBASEISN | fCOMPNAME | fAPICLIENTID |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 951 | 2025-12-03 09:30:20.763 | 52 | _VUP | _VER | X տարբերակի փոփոխություն: | -1 | -1 | 2025-10-15 11:44:31.607 | TEST | 2 |

## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| iAPPLOG1 | Unique, Clustered | fROWID |
| iAPPLOG2 | Non-Unique, Non-Clustered | fDATE, fMODCODE, fOPERCODE |
| iAPPLOG3 | Non-Unique, Non-Clustered | fOBJISN |
| iAPPLOG4 | Non-Unique, Non-Clustered | fBASEISN |
