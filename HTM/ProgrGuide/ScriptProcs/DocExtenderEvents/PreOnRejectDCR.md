---
layout: page
title: "PreOnRejectDCR իրադարձություն"
---

# PreOnRejectDCR փաստաթղթի օգտագործողի կողմից ընդլայնվող իրադարձություն

PreOnRejectDCR իրադարձությունը առաջանում է փաստաթղթի փոփոխման հայտը մերժելիս` [OnRejectDCR](../OnRejectDCR.md) իրադարձությունից առաջ։

Իրադարձությունը կանչվում է տրանզակցիայի ընթացքում։

## Շարահյուսություն

``` vb
Public Sub PreOnRejectDCR(ByVal oEventArgsDocOnRejectDCR As EventArgsDocOnRejectDCR) 
    ' statements
End Sub
```

Բաղադրիչներն են՝

|Պարամետր|Նկարագրություն|
|--|--|
|`oEventArgsDocOnRejectDCR`| [EventArgsDocOnRejectDCR](../UserDefinedHandlers.md#eventargsdoconrejectdcr-class) դասի օբյեկտ։ |

## Օրինակ

```vb
Public Sub PreOnRejectDCR(ByVal oEventArgsDocOnRejectDCR As EventArgsDocOnRejectDCR)
   If oEventArgsDocOnRejectDCR.DCR.DCRID > 100 Then
	RaiseError Doc.Caption, "Փաստաթղթի փոփոխման հայտի մերժումը արգելված է", _
		    Doc.ECaption, "Document's change request denial is not allowed"
   End If
End Sub
```