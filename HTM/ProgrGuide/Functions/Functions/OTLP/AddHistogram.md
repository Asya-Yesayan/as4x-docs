---
layout: page
title: AsKernel/AddHistogram
tags: [trace, metric, OTLP]
---

# AddHistogram մեթոդ

Ստեղծում է նոր հիստոգրամ։ Հիստոգրամում արժեք գրանցելու և այն փակելու համար անհրաժեշտ է օգտագործել [RecordHistogram](RecordHistogram.md) մեթոդը։

## Շարահյուսություն

```vb
Public Sub AddHistogram(ByVal sId As String,
               Optional ByVal sUnit As String = "",
               Optional ByVal sDescription As String = "")
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Հիստոգրամի id-ն: |
| sUnit | Հիստոգրամում օգտագործվող չափման միավորը (Օրինակ "ms" - միլիվայրկյան, "s" - վայրկյան, "min" - րոպե...): |
| sDescription | Հիստոգրամի նկարագրությունը: |

**Օրինակ**

```vb
Public Sub Test()
Dim oStopWatch      As StopWatch
Dim dictTags      As Dictionary
Dim dicRespnonse       As Dictionary

Set dicRespnonse = New Dictionary
Set dictTags = New Dictionary
dictTags.Add "Method", "GET"

AddHistogram "GetList_API_ResponseTime", "ms", "Tracks GetList API response time"
Set oStopWatch = New StopWatch

ExecuteService "api/DPR", Nothing, dicRespnonse, "GET"
RecordHistogram "GetList_API_ResponseTime", oStopWatch.Elapsed , dictTags

End Sub
```

