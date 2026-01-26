---
layout: page
title: NOTIFICATIONSUBSCRIBERS աղյուսակ
---

Այս աղյուսակը նախատեսված է ծանուցման խմբերի օգտագործողների ինֆորմացիայի պահպանման համար։

| Սյան անվանում          | Տվյալների տիպ | Null      | Նկարագրություն |
|-----------------------|--------------|-----------|----------------|
| fGROUPID              | int          | not null  | Ծանուցման խմբի կոդը (id)։ |
| fNOTIFICATIONTYPE     | smallint  | not null  | Ծանուցման եղանակը։ <br> **0** - Առանց ծանուցում։ <br> **1** - Էլեկտրոնային փոստով։ |
| fSUBSCRIBER           | varchar(512) | not null  | Ծանուցվող օգտագործողի Էլեկտրոնային հասցեն։ |

**Օրինակ**

| fGROUPID | fNOTIFICATIONTYPE | fSUBSCRIBER |
| --- | --- | --- | 
| 3 | 1 | testUser@gmail.com |
| 3 | 1 | User52@gmail.com |

## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| PK_SUBSCRIBERS | Unique, Clustered   | fGROUPID, fNOTIFICATIONTYPE, fSUBSCRIBER     |




