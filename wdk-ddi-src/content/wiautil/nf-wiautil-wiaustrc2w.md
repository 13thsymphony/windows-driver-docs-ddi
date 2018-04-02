---
UID: NF:wiautil.wiauStrC2W
title: wiauStrC2W function
author: windows-driver-content
description: The wiauStrC2W function converts an ANSI character string to a Unicode string.
old-location: image\wiaustrc2w.htm
old-project: image
ms.assetid: 66d90248-c496-44c8-98f4-5eb3e2cae130
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaustrc2w, wiauFncs_acd27425-a431-42a0-8317-514ea7904ace.xml, wiauStrC2W, wiauStrC2W function [Imaging Devices], wiautil/wiauStrC2W
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
-	wiautil.h
api_name:
-	wiauStrC2W
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauStrC2W function
The <b>wiauStrC2W</b> function converts an ANSI character string to a Unicode string.

## Syntax

```
HRESULT wiauStrC2W(
  CHAR  *pszSrc,
  WCHAR *pwszDst,
  INT   iSize
);
```

## Parameters

`pszSrc`

Points to the ANSI string to convert.

`pwszDst`

Pointer to a memory location that receives the converted Unicode string.

`iSize`

Specifies the size, in bytes, of the buffer pointed to by <i>pwszDst</i>.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550183">wiauStrC2C</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550187">wiauStrW2C</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550189">wiauStrW2W</a>