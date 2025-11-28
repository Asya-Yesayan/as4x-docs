---
layout: page
title: "ConfigureDCRFields իրադարձություն"
---

# ConfigureDCRFields փաստաթղթի համակարգային իրադարձություն

[Տես նաև](../scriptstproced.md) Օրինակ [Կիրառվում է](../Defs/doc.md)

Այս իրադարձությունը թույլ է տալիս որոշել, թե փաստաթղթի որ դաշտերի փոփոխությունները պետք է ցուցադրվեն տեքստային հաշվետվությունում, որը բացվում է **«Փաստաթղթի պատմություն»** դիտելու ձևի **«Դիտել փոփոխությունները տեքստային»** կոնտեքստային ֆունկցիաներով։

Լռությամբ տեքստային հաշվետվությունում ցուցադրվում են այն դաշտերը, որոնք չունեն **H** ատրիբուտը։

## Շարահյուսություն

```vb
Public Sub ConfigureDCRFields(ByVal oEventArgsDocConfigureDCRFields As EventArgsDocConfigureDCRFields)

End Sub
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
| --- | --- |
| oEventArgsDocConfigureDCRFields | [EventArgsDocConfigureDCRFields](UserDefinedHandlers.md#eventargsdocconfiguredcrfields-class) դասի օբյեկտ։ |

**Օրինակ**

```vb
Public Sub ConfigureDCRFields(ByVal oEventArgsDocConfigureDCRFields As EventArgsDocConfigureDCRFields)
	oEventArgsDocConfigureDCRFields.FieldInclusions.Add("Code", True)
	oEventArgsDocConfigureDCRFields.FieldInclusions.Add("Number", False)
End Sub
```
