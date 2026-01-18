---
layout: page
title: "PostUIValidate իրադարձություն"
---

# PostUIValidate փաստաթղթի օգտագործողի կողմից ընդլայնվող իրադարձություն

PostUIValidate իրադարձությունը առաջանում է փաստաթուղթը ինտերֆեյսից գրանցելիս` [UIValidate](../UIValidate.md) իրադարձությունից հետո (նախքան [գրանցման տրանզակցիայի](../../Functions/ASDOC/Store.md) բացվելը)։

Հիմնականում օգտագործվում է փաստաթղթի դաշտերի արժեքների ճշգրտման և ստուգման նպատակով։

## Շարահյուսություն

``` vb
Public Sub PostUIValidate(ByVal oEventArgsDocUIValidate As EventArgsDocUIValidate) 
    ' statements
End Sub
```

Բաղադրիչներն են՝

|Պարամետր|Նկարագրություն|
|--|--|
|`oEventArgsDocUIValidate`| [EventArgsDocUIValidate](../UserDefinedHandlers.md#eventargsdocuivalidate-class) դասի օբյեկտ: |

**Օրինակ**

```vb
Public Sub PostUIValidate(ByVal oEventArgsDocUIValidate As EventArgsDocUIValidate)
	If oEventArgsDocUIValidate.Doc.Grid("Accs").RowCount = 0 Then
		If AsMsgBox("Հաշիվներ աղյուսակը դատարկ է։ Շարունակե՞լ։", vbYesNo + vbNo, "Տվյալների հաստատում",, _
			"Accounts table is empty. Do You want to continue?", "Data verification") = vbNo Then
			BreakError
		End If
	End If
End Sub
```
