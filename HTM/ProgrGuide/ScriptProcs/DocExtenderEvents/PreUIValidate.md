---
layout: page
title: "PreUIValidate իրադարձություն"
---

# PreUIValidate փաստաթղթի օգտագործողի կողմից ընդլայնվող իրադարձություն

PostUIValidate իրադարձությունը առաջանում է փաստաթուղթը ինտերֆեյսից գրանցելիս` [UIValidate](../UIValidate.md) իրադարձությունից առաջ (նախքան [գրանցման տրանզակցիայի](../../Functions/ASDOC/Store.md) բացվելը)։

Հիմնականում օգտագործվում է փաստաթղթի դաշտերի արժեքների ճշգրտման և ստուգման նպատակով։

## Շարահյուսություն

``` vb
Public Sub PreUIValidate(ByVal oEventArgsDocUIValidate As EventArgsDocUIValidate) 
    ' statements
End Sub
```

Բաղադրիչներն են՝

|Պարամետր|Նկարագրություն|
|--|--|
|`oEventArgsDocUIValidate`| [EventArgsDocUIValidate](../UserDefinedHandlers.md#eventargsdocuivalidate-class) դասի օբյեկտ։ |

```vb
Public Sub PreUIValidate(ByVal oEventArgsDocUIValidate As EventArgsDocUIValidate)
	If Trim(oEventArgsDocUIValidate.Doc("CODE")) = "" Then
		oEventArgsDocUIValidate.Doc.SetFocus "CODE"
		RaiseError "Սխալ", "Պայմանագրի համարը լրացված չէ", _ 
                   "Error", "Agreement's code is not filled"
	End If
End Sub
```