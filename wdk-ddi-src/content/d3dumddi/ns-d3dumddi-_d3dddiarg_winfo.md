---
UID: NS:d3dumddi._D3DDDIARG_WINFO
title: "_D3DDDIARG_WINFO"
author: windows-driver-content
description: The D3DDDIARG_WINFO structure describes a w range for w buffering.
old-location: display\d3dddiarg_winfo.htm
old-project: display
ms.assetid: 82ab59d7-302a-4e3a-b5e6-6a332eafcbed
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_WINFO, D3DDDIARG_WINFO structure [Display Devices], UMDisplayDriver_param_Structs_6ab282fa-6a76-4712-83d5-77638adb2b7a.xml, _D3DDDIARG_WINFO, d3dumddi/D3DDDIARG_WINFO, display.d3dddiarg_winfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_WINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_WINFO
---

# _D3DDDIARG_WINFO structure
The D3DDDIARG_WINFO structure describes a w range for w buffering.

## Syntax
```
typedef struct _D3DDDIARG_WINFO {
  FLOAT WNear;
  FLOAT WFar;
} D3DDDIARG_WINFO;
```

## Members


`WNear`

[in] A FLOAT value that indicates the near limit in the w range.

`WFar`

[in] A FLOAT value that indicates the far limit in the w range.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/e9cd87b9-3958-4b10-895d-480e03ebea76">UpdateWInfo</a>