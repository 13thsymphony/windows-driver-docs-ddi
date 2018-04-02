---
UID: NF:filterpipeline.IPartFont2.GetFontRestriction
title: IPartFont2::GetFontRestriction method
author: windows-driver-content
description: "."
old-location: print\ipartfont2_getfontrestriction.htm
old-project: print
ms.assetid: C6289E38-281A-46A2-8E28-138A20BF6684
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetFontRestriction method [Print Devices], GetFontRestriction method [Print Devices], IPartFont2 interface, GetFontRestriction,IPartFont2.GetFontRestriction, IPartFont2, IPartFont2 interface [Print Devices], GetFontRestriction method, IPartFont2::GetFontRestriction, filterpipeline/IPartFont2::GetFontRestriction, print.ipartfont2_getfontrestriction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Filterpipeline.h
api_name:
-	IPartFont2.GetFontRestriction
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# IPartFont2::GetFontRestriction method


## Syntax

```
HRESULT GetFontRestriction(
  EXpsFontRestriction *pRestriction
);
```

## Parameters

`pRestriction`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | filterpipeline.h |

## See Also

<a href="https://msdn.microsoft.com/AB1EFF6E-4FF5-413E-A4E4-3EEC47CDEBD4">IPartFont2</a>