---
layout: page
title: AsKernel/RecordHistogram
tags: [trace, metric, OTLP]
---

# RecordHistogram մեթոդ

Գրանցում է հիստոգրամի արժեքը և փակում այն։ Հիստոգրամը պետք է նախապես ստեղծված լինի [AddHistogram](AddHistogram.md) մեթոդով։

## Շարահյուսություն

```vb
Public Sub RecordHistogram(ByVal sId As String,
                           ByVal dValue As Double,
                  Optional ByVal dictAdditionalInfo As Dictionary)
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Հիստոգրամի id-ն: |
| dValue | Գրանցվող թվային արժեքը։ |
| dictAdditionalInfo | Dictionary տիպի օբյեկտ, որը նախատեսված է լրացուցիչ tag-երի անունների և արժեքների ավելացման համար։ <br> Համակարգում առկա են հիմնական tag-եր, որոնք լրացվում են ավտոմատ (ծրագրի, սերվերի, տվյալների բազայի ու մեքենայի անունները, օգտագործողի համարը...)։ |

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
