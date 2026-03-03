---
layout: page
title: AsKernel/StopActivity
tags: [trace, metric, OTLP]
---

# StopActivity մեթոդ

Փակում է [նախապես բացված թրեյսը](StartActivity.md)՝ ըստ թրեյսի id-ի։ Թրեյսի id-ն չտրամադրելու դեպքում փակում է ընթացիկ թրեյսը։

## Շարահյուսություն

```vb
Public Sub StopActivity(Optional ByVal sId As String = "")
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| sId | Թրեյսի id-ն։ |

**Օրինակ**

```vb
Dim sActivityID As String
    sActivityID = StartActivity "AddSettingTypeInFolder function execution"
	    Call RunSub ("SETTINGS","AddSettingTypeInFolder", Doc, Doc.Caption, Doc.ECaption)
	StopActivity sActivityID
```