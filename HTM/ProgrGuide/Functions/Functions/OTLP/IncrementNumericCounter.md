---
layout: page
title: AsKernel/IncrementNumericCounter
tags: [trace, metric, OTLP]
---

# IncrementNumericCounter մեթոդ

Ավելացնում է [AddNumericCounter](AddNumericCounter.md) մեթոդով ստեղծված թվային counter-ի արժեքը նշված չափով։

## Շարահյուսություն

```vb
Public Sub IncrementNumericounter(ByVal sId As String,
                                  ByVal lValue As Long,
                         Optional ByVal dictAdditionalInfo As Dictionary)
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Counter-ի id-ն։ |
| lValue | Արժեքի ավելացման չափը։ |
| dictAdditionalInfo | Dictionary տիպի օբյեկտ, որը նախատեսված է լրացուցիչ tag-երի անունների և արժեքների ավելացման համար։ <br> Համակարգում առկա են հիմնական tag-եր, որոնք լրացվում են ավտոմատ (ծրագրի, սերվերի, տվյալների բազայի ու մեքենայի անունները, օգտագործողի համարը...)։ |

**Օրինակ**

```vb
Dim processResult As Long
Dim additionalInfo As Dictionary

AddNumericCounter "sample_ProcessedItems", "Processed Items"

processResult = RunSub ("SETTINGS", "ProcesseItems")

Set additionalInfo = New Dictionary
additionalInfo.Add "ItemType", "Invoice"

IncrementNumericCounter "sample_ProcessedItems", processResult, additionalInfo
```