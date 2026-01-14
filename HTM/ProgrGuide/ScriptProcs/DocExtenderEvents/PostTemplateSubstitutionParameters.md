---
layout: page
title: "PostTemplateSubstitutionParameters իրադարձություն"
---

# TemplateSubstitutionParameters փաստաթղթի օգտագործողի կողմից ընդլայնվող իրադարձություն

[Տես նաև](../TemplateSubstitution.md) Օրինակ [Կիրառվում է](../../Defs/doc.md)

PostTemplateSubstitutionParameters իրադարձությունը առաջանում է փաստաթղթի տպելու ձևանմուշի լրացման ժամանակ` [TemplateSubstitutionParameters](../TemplateSubstitutionParameters.md) իրադարձության կանչից հետո։ 

Մշակիչի **oEventArgsDocTempSubParameters․Parameters** պարամետրում անհրաժեշտ է ավելացնել պարամետրեր, որոնք օգտագործվելու են տպելու ձևանմուշի հաշվարկման ժամանակ՝ [TemplateSubstitution](../TemplateSubstitution.md) իրադարձությունում։ 

Եթե տպելու ձևանմուշներ են ձևավորվում թղթապանակում նշված մի քանի փաստաթղթերի համար, ապա այս իրադարձությունը աշխատում է միայն մեկ անգամ, իսկ [TemplateSubstitution](../TemplateSubstitution.md) իրադարձությունը աշխատում է յուրաքանչյուր փաստաթղթի համար։

## Շարահյուսություն

```vb
Public Sub PostTemplateSubstitutionParameters(ByVal args As EventArgsDocTempSubParameters)  
    ' statements
End Sub
```

Բաղադրիչներն են՝

|Պարամետր|Նկարագրություն|
|--|--|
|`oEventArgsDocTempSubParameters`| [EventArgsDocTempSubParameters](../UserDefinedHandlers.md#eventargsdoctempsubparameters-class) դասի օբյեկտ: |

## Օրինակ

```vb
Public Sub PostTemplateSubstitutionParameters(ByVal args As EventArgsDocTempSubParameters)
	args.Parameters.Add("Date", #1/15/2020#)
	args.Parameters.Add("Name", "Test")
End Sub
```
