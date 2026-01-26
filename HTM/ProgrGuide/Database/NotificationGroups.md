---
layout: page
title: NOTIFICATIONGROUPS աղյուսակ
---

Այս աղյուսակը նախատեսված է ծանուցման խմբերի ինֆորմացիայի պահպանման համար։

| Սյան անվանում    | Տվյալների տիպ      | Null       | Նկարագրություն |
|------------------|---------------------|-----------|----------------|
| fGROUPID         | int                 | not null  | Ծանուցման խմբի կոդը (id): Լրացվում է ավտոմատ կերպով՝ աղյուսակում նոր տող ավելացնելիս (identity column):   |
| fNAME            | varchar(100)        | not null  | Ծանուցման խմբի անվանումը։ |
| fDESCRIPTION     | nvarchar(250)       | null      | Ծանուցման խմբի նկարագրությունը։ |

**Օրինակ**

| fGROUPID | fNAME | fDESCRIPTION |
| --- | --- | --- | 
| 3 | Configuration Changes | Կոնֆիգուրացիայի փոփոխությունների ծանուցումներ |

## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| PK_fGROUPID | Unique, Clustered   | fGROUPID     |
| UQ_fNAME | Unique, NonClustered   | fNAME     |




