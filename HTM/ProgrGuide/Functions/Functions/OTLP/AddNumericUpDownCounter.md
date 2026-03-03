---
layout: page
title: AsKernel/AddNumericUpDownCounter
tags: [trace, metric, OTLP]
---

# AddNumericUpDownCounter մեթոդ

Ստեղծվում է թվային counter, որի արժեքը կարող է աճել կամ նվազել։

Counter-ի արժեքը ավելացնելու համար անհրաժեշտ է կանչել [IncrementNumericUpDownCounter](IncrementNumericUpDownCounter.md), իսկ նվազեցնելու համար՝ [DecrementNumericUpDownCounter](DecrementNumericUpDownCounter.md) մեթոդը։

## Շարահյուսություն

```vb
Public Sub AddNumericUpDownCounter(ByVal sId As String, Optional ByVal sDescription As String = "")
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Counter-ի id-ն։ |
| sDescription | Counter-ի նկարագրությունը։ |

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