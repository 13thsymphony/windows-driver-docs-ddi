---
UID: NS:d3dumddi._D3DDDIARG_DESTROYCRYPTOSESSION
title: "_D3DDDIARG_DESTROYCRYPTOSESSION"
author: windows-driver-content
description: The D3DDDIARG_DESTROYCRYPTOSESSION structure contains the handle to an encryption session that is destroyed in a call to the DestroyCryptoSession function.
old-location: display\d3dddiarg_destroycryptosession.htm
old-project: display
ms.assetid: 7ae8bfd7-da94-41b0-8995-34194b2ad8a7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_DESTROYCRYPTOSESSION, D3DDDIARG_DESTROYCRYPTOSESSION structure [Display Devices], UMDisplayDriver_param_Structs_75cddfac-f1d8-4378-bb94-441fff43e224.xml, _D3DDDIARG_DESTROYCRYPTOSESSION, d3dumddi/D3DDDIARG_DESTROYCRYPTOSESSION, display.d3dddiarg_destroycryptosession
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DESTROYCRYPTOSESSION is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_DESTROYCRYPTOSESSION
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DESTROYCRYPTOSESSION
---

# _D3DDDIARG_DESTROYCRYPTOSESSION structure
The D3DDDIARG_DESTROYCRYPTOSESSION structure contains the handle to an encryption session that is destroyed in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451632">DestroyCryptoSession</a> function.

## Syntax
```
typedef struct _D3DDDIARG_DESTROYCRYPTOSESSION {
  HANDLE hCryptoSession;
} D3DDDIARG_DESTROYCRYPTOSESSION;
```

## Members


`hCryptoSession`

[in] The handle to the encryption session that the driver destroys.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDIARG_DESTROYCRYPTOSESSION is supported beginning with the Windows 7 operating system. D3DDDIARG_DESTROYCRYPTOSESSION is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451632">DestroyCryptoSession</a>