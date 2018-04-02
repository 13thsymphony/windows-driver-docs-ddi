---
UID: NS:d3dumddi._DXVADDI_PRIVATEBUFFER
title: "_DXVADDI_PRIVATEBUFFER"
author: windows-driver-content
description: The DXVADDI_PRIVATEBUFFER structure describes a private buffer that a nonstandard decoder uses to perform a decode operation.
old-location: display\dxvaddi_privatebuffer.htm
old-project: display
ms.assetid: 3e41472c-4c9d-4727-af08-a350e1967ef0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_90012dba-8a0c-4685-a528-1a57265e5688.xml, DXVADDI_PRIVATEBUFFER, DXVADDI_PRIVATEBUFFER structure [Display Devices], _DXVADDI_PRIVATEBUFFER, d3dumddi/DXVADDI_PRIVATEBUFFER, display.dxvaddi_privatebuffer
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
-	DXVADDI_PRIVATEBUFFER
product: Windows
targetos: Windows
req.typenames: DXVADDI_PRIVATEBUFFER
---

# _DXVADDI_PRIVATEBUFFER structure
The DXVADDI_PRIVATEBUFFER structure describes a private buffer that a nonstandard decoder uses to perform a decode operation.

## Syntax
```
typedef struct _DXVADDI_PRIVATEBUFFER {
  HANDLE hResource;
  UINT   SubResourceIndex;
  UINT   DataOffset;
  UINT   DataSize;
} DXVADDI_PRIVATEBUFFER;
```

## Members


`hResource`

[in] A handle to the resource that contains the private buffer for the decode operation.

`SubResourceIndex`

[in] The index to the private buffer within the resource.

`DataOffset`

[in] The offset to the relevant data, in bytes, from the beginning of the buffer.

`DataSize`

[in] The size of the relevant data, in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543009">D3DDDIARG_DECODEEXTENSIONEXECUTE</a>