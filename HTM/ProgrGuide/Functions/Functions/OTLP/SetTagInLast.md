---
layout: page
title: AsKernel/SetTagInLast
tags: [trace, metric, OTLP]
---

# SetTagInLast մեթոդ

Վերջին [բացված թրեյսի](StartActivity.md) վրա ավելացնում է նշված tag-ը և նրա արժեքը։

## Շարահյուսություն

```vb
Public Sub SetTagInLast(ByVal sTagId As String, ByVal sTagValue As String)
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sTagId | Ավելացվող tag-ի անունը: |
| sTagValue | Նշանակվող արժեքը։ |

**Օրինակ**

```vb
Dim rs As AsDataTable
Dim sActivityID As String
Dim sSql As String


sSql = "select fSUID, NAME from USERS where fADM = 1"
sActivityID = StartActivity("Execute GetAdminUsers SQL")
Set rs = dbc.OpenDataTable(sSql, 900)
SetTagInLast "GetActiveUsers RowCount", CStr(rs.RowCount)
StopActivity sActivityID
```