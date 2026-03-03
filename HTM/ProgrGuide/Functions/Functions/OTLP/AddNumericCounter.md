---
layout: page
title: AsKernel/AddNumericCounter
tags: [trace, metric, OTLP]
---

# AddNumericCounter մեթոդ

Ստեղծում է թվային counter, որի արժեքը կարող է միայն աճել:

Counter-ի արժեքը փոփոխելու համար անհրաժեշտ է կանչել [IncrementNumericCounter](IncrementNumericCounter.md) մեթոդը։

## Շարահյուսություն

```vb
Public Sub AddNumericCounter(ByVal sId As String, Optional ByVal sDescription As String = "")
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Counter-ի id-ն։ |
| sDescription | Counter-ի նկարագրությունը։ |

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