---
UID: NS:wiamindr_lh._WIAS_ENDORSER_INFO
title: "_WIAS_ENDORSER_INFO"
author: windows-driver-content
description: The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs.
old-location: image\wias_endorser_info.htm
old-project: image
ms.assetid: 4874ddab-5443-4e03-8f49-493682dabac1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWIAS_ENDORSER_INFO, PWIAS_ENDORSER_INFO, PWIAS_ENDORSER_INFO structure pointer [Imaging Devices], WIAS_ENDORSER_INFO, WIAS_ENDORSER_INFO structure [Imaging Devices], _WIAS_ENDORSER_INFO, image.wias_endorser_info, wiamindr_lh/PWIAS_ENDORSER_INFO, wiamindr_lh/WIAS_ENDORSER_INFO, wiastrct_de79ab57-ad51-4bf0-90cb-51bd1a8352bd.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	HeaderDef
api_location:
-	wiamindr_lh.h
api_name:
-	WIAS_ENDORSER_INFO
product: Windows
targetos: Windows
req.typenames: WIAS_ENDORSER_INFO, *PWIAS_ENDORSER_INFO
req.product: Windows 10 or later.
---

# _WIAS_ENDORSER_INFO structure
The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs.

## Syntax
```
typedef struct _WIAS_ENDORSER_INFO {
  ULONG               ulPageCount;
  ULONG               ulNumEndorserValues;
  WIAS_ENDORSER_VALUE *pEndorserValues;
} WIAS_ENDORSER_INFO, *PWIAS_ENDORSER_INFO;
```

## Members


`ulPageCount`

Specifies the value that will replace the $PAGE_COUNT$ token, provided that the endorser string contains that token.

`ulNumEndorserValues`

Specifies the number of token/value pairs. This member will be 0 if there are no custom token/value pairs.

`pEndorserValues`

Points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff549562">WIAS_ENDORSER_VALUE</a> structures, holding custom token/value pairs. If the value of the <b>ulNumEndorserValues</b> member is 0, this member should be <b>NULL</b>.

## Remarks
Currently, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549282">wiasParseEndorserString</a> recognizes three endorser tokens: $DATE$, $TIME$, $PAGE_COUNT$, $DAY$, $MONTH$, and $YEAR$. (See <i>wiamdef.h</i>.) Any other tokens and their values must be specified in the <b>pEndorserValues</b> member of this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems. Available in Windows Me and in Windows XP and later versions of the Windows operating systems. |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549562">WIAS_ENDORSER_VALUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549282">wiasParseEndorserString</a>