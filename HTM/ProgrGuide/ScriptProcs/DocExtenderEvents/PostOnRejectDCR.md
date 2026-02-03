---
layout: page
title: "PostOnRejectDCR իրադարձություն"
---

# PostOnRejectDCR փաստաթղթի օգտագործողի կողմից ընդլայնվող իրադարձություն

PostOnRejectDCR իրադարձությունը առաջանում է փաստաթղթի փոփոխման հայտը մերժելիս` [OnRejectDCR](../OnRejectDCR.md) իրադարձությունից հետո։ Հնարավորություն է տալիս փոփոխել փաստաթղթի և փոփոխման հայտի հատկությունները, թարմացնել մերժման մեկնաբանությունը։

Իրադարձությունը կանչվում է մերժման տրանզակցիայի ընթացքում։

## Շարահյուսություն

``` vb
Public Sub PostOnRejectDCR(ByVal oEventArgsDocOnRejectDCR As EventArgsDocOnRejectDCR) 
    ' statements
End Sub
```

Բաղադրիչներն են՝

|Պարամետր|Նկարագրություն|
|--|--|
|`oEventArgsDocOnRejectDCR`| [EventArgsDocOnRejectDCR](../UserDefinedHandlers.md#eventargsdoconrejectdcr-class) դասի օբյեկտ։ |

## Օրինակ

```vb
Public Sub PostOnRejectDCR(ByVal oEventArgsDocOnRejectDCR As EventArgsDocOnRejectDCR) 
    oEventArgsDocOnRejectDCR.DCR.ReFolderDocument = True
End Sub
```