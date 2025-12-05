---
layout: page
title: "AsData/OpenCursor"
---

# OpenCursor մեթոդ

[См. также](../Asdata.md) [Пример](../../Examples/E_AsData.md) [Применяется к](../Asdata.md)

Բացում է նշորդ(Cursor) տվյալների աղբյուրի աղյուսակային տվյալների վրա։ 
Նշորդի միջոցով հնարավոր է տող առ տող կարդալ աղյուսակային տվյալները։

## Շարահյուսություն

``` vb
object.OpenCursor([CursorType], [LockType], [Indicate], [lConnectionType], [arrColumnsNames], [bAddPermanents], [oExtenderInfo])
```

Բաղադրիչներն են՝

| Պարամետր | Նկարագրություն |
|--|--|
| object| Տվյալների աղբյուրի հղում։  |
| CursorType | Տվյալների աղբյուրի նշորդի բացման [եղանակը](../../Constants/const_opencursor_cursortype.md)։ | 
| LockType | Ընթերցվող տվյալների վրա դրվող [SQL կողպեքի (lock) տիպը](../../Constants/const_opencursor_locktype.md)։ |
| Indicate | Ընթացքի [ցուցադրման ձև](../../Constants/const_opencursor_Indicate.md)։ Փոխանցված չլինելու դեպքում օգտագործվում [տվյալների աղյուրի նկարագրության մեջ](../../Defs/Data.md) տրված ձևը։ | 
| lConnectionType | Տվյալների աղբյուրի հաշվարկում օգտագործվող Sql միացման [տեսակը](../../Constants/ConnectionType.md)։ Լռությամբ արժեքը **Connection_DS** է։ |
| arrColumnsNames | Այն սյուների ներքին անունների ցուցակը, որոնք պետք է վերադարձվեն տվյալների աղբյուրի կատարման արդյունքում։ |
| bAddPermanents | Տվյալների աղբյուրի կատարման արդյունքում հավերժական (permanent) սյուների ներառման հայտանիշ։  |
| oExtenderInfo | Տվյալների աղբյուրի [ընդլայնման նկարագրությունը](../ExtenderInfo.md), որը կիրառվելու է տվյալների աղբյուրը հաշվարկելիս: |

## Օրինակ

```vb
Sub ExecuteDSWithExtender()
	Dim oData As AsData
	Dim oExtender As ExtenderInfo
	Dim dSColumns() As String
	Dim extenderColumns() As String

    ' տվյալների աղբյուրի ցուցադրվող սյուների անուններ
	ReDim dSColumns(1)
	dSColumns(0) = "fISN"
	dSColumns(1) = "fNAME"

    ' տվյալների աղբյուրի ընդլայնման ցուցադրվող սյուների անուններ
	ReDim extenderColumns(0)
	extenderColumns(0) = "Filial"

    ' ընդլայնման նկարագրության սահմանում
	Set oExtender = New ExtenderInfo
    ' ընդլայնման ներքին անունը
	oExtender.Name = "DeletedExtended" 
    ' ընդլայնման պարամետրի ներքին անունը, տիպը, արժեքը
	oExtender.AddExtendedParam("DocumentType","C(8)","TemplUDP")
    ' ընդլայնման ցուցադրվող սյուների ավելացում
	oExtender.AddExtendedColumns(extenderColumns)

    ' տվյալների աղբյուրի սահմանում
	Set oData = Data("DelDoc")
	With oData
        ' տվյալների աղբյուրի պարամետրերի արժեքավորում
		.Parameters("StartDate") = #1/1/2022#
		.Parameters("EndDate") = #12/1/2025#
        ' տվյալների աղբյուրի կատարում ընդլայնումով
		.OpenCursor(,,,, dSColumns, True, oExtender)
	End With

End Sub
```

