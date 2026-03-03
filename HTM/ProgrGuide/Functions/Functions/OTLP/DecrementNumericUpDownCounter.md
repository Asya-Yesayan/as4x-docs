---
layout: page
title: AsKernel/DecrementNumericUpDownCounter
tags: [trace, metric, OTLP]
---

# DecrementNumericUpDownCounter մեթոդ

Նվազեցնում է [AddNumericUpDownCounter](AddNumericUpDownCounter.md) մեթոդով ստեղծված թվային counter-ի արժեքը նշված չափով։

## Շարահյուսություն

```vb
Public Sub DecrementNumericUpDownCounter(ByVal sId As String,
                                         ByVal lValue As Long,
                                Optional ByVal dictAdditionalInfo As Dictionary)
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Counter-ի id-ն։ |
| lValue | Արժեքի նվազեցման չափը։ |
| dictAdditionalInfo | Dictionary տիպի օբյեկտ, որը նախատեսված է լրացուցիչ tag-երի անունների և արժեքների ավելացման համար։ <br> Համակարգում առկա են հիմնական tag-եր, որոնք լրացվում են ավտոմատ (ծրագրի, սերվերի, տվյալների բազայի ու մեքենայի անունները, օգտագործողի համարը...)։ |

**Օրինակ**

```vb
Dim lProcessedCount As Long
Dim dictTags As Dictionary

AddNumericUpDownCounter "OrdersProcessed", "Number of orders processed"

lProcessedCount = 5

Set dictTags = New Dictionary
dictTags.Add "Department", "Sales"
dictTags.Add "Priority", "High"

IncrementNumericUpDownCounter "OrdersProcessed", lProcessedCount, dictTags

DecrementNumericUpDownCounter "OrdersProcessed", 2, dictTags
```
