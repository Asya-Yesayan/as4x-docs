---
layout: page
title: AsKernel/StartActivity
tags: [trace, metric, OTLP]
---

# StartActivity մեթոդ

Բացում է թրեյս և վերադարձնում բացված թրեյսի id-ն։

## Շարահյուսություն

```vb
Public Function StartActivity(ByVal sCaption As String) As String
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sCaption | Թրեյսի անվանումը։ |

**Օրինակ**

```vb
Dim sActivityID As String
    sActivityID = StartActivity "AddSettingTypeInFolder function execution"
	    Call RunSub ("SETTINGS","AddSettingTypeInFolder",Doc,Doc.Caption, Doc.ECaption)
	StopActivity sActivityID
```