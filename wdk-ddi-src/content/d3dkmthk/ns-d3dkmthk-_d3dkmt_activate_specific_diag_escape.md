---
UID: NS:d3dkmthk._D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE
title: "_D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE"
author: windows-driver-content
description: Indicates an escape type that is to be activated or deactivated.
old-location: display\d3dkmt_activate_specific_diag_escape.htm
old-project: display
ms.assetid: e3c61b33-2e10-42cf-b9e8-fe70a43573e8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE, D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE structure [Display Devices], _D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE, d3dkmthk/D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE, display.d3dkmt_activate_specific_diag_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE
---

# _D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE structure
Indicates an escape type that is to be activated or deactivated.

## Syntax
```
typedef struct _D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE {
  D3DKMT_ACTIVATE_SPECIFIC_DIAG_TYPE Type;
  BOOL                               Activate;
} D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE;
```

## Members


`Type`

The <a href="https://msdn.microsoft.com/db57ae5e-7060-4d45-99a5-e54c82b0aa05">D3DKMT_ESCAPETYPE</a> escape type  that needs to be activated or deactivated.

`Activate`

If <b>TRUE</b>, the escape type is to be activated. If <b>FALSE</b>, the escape type is to be deactivated.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h |

## See Also

<a href="https://msdn.microsoft.com/db57ae5e-7060-4d45-99a5-e54c82b0aa05">D3DKMT_ESCAPETYPE</a>