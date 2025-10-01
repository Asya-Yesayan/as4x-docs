---
layout: page
title: SESSIONINFO աղյուսակ
---

Այս աղյուսակը նախատեսված է [սեսսիաների](https://armsoft.github.io/as8x-docs/src/server_api/types/SessionInfo.html) ինֆորմացիայի պահպանման համար։

| Սյան անվանում | Տվյալների տիպ | Null | Նկարագրություն |
| --- | --- | --- | --- |
| fGUID | uniqueidentifier | not null | [Սեսսիայի](https://armsoft.github.io/as8x-docs/src/server_api/types/SessionInfo.html) ներքին նույնակականացման համարը ([GUID](https://learn.microsoft.com/en-us/dotnet/api/system.guid#remarks)):|
| fINFO | varchar(max) | not null | [Սեսսիայի](https://armsoft.github.io/as8x-docs/src/server_api/types/SessionInfo.html) ինֆորմացիան (օգտագործողի ներքին անուն, համակարգչի անուն․․․) կոդավորված տեսքով։ |
| fENDDATE | datetime | not null | [Սեսսիայի](https://armsoft.github.io/as8x-docs/src/server_api/types/SessionInfo.html) վավերականության ժամկետի ավարտի ամսաթիվը/ժամանակը։ |
| fLASTACTIVEDATE | datetime | not null | [Սեսսիայի](https://armsoft.github.io/as8x-docs/src/server_api/types/SessionInfo.html) վերջին ակտիվության ամսաթիվը/ժամանակը։ |

## Ինդեքսներ

| Անվանում | Տիպ | Սյուների անուններ |
| --- | --- | --- |
| iSESSIONINFO1 | Unique, Clustered | fGUID |
