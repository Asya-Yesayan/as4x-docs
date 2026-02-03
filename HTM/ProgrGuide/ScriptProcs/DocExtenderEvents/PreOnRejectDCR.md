---
layout: page
title: "PreOnRejectDCR իրադարձություն"
---

# PreOnRejectDCR փաստաթղթի օգտագործողի կողմից ընդլայնվող իրադարձություն

PreOnRejectDCR իրադարձությունը առաջանում է փաստաթղթի փոփոխման հայտը մերժելիս` [OnRejectDCR](../OnRejectDCR.md) իրադարձությունից առաջ։ Հնարավորություն է տալիս փոփոխել փաստաթղթի և փոփոխման հայտի հատկությունները, թարմացնել մերժման մեկնաբանությունը։

Իրադարձությունը կանչվում է մերժման տրանզակցիայի ընթացքում։

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