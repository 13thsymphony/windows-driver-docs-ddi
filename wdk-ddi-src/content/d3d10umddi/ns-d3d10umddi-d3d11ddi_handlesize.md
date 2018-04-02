---
UID: NS:d3d10umddi.D3D11DDI_HANDLESIZE
title: D3D11DDI_HANDLESIZE
author: windows-driver-content
description: The D3D11DDI_HANDLESIZE structure describes a handle.
old-location: display\d3d11ddi_handlesize.htm
old-project: display
ms.assetid: 9b785bee-289f-4f91-8183-c1dc2fa1fa6d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11DDI_HANDLESIZE, D3D11DDI_HANDLESIZE structure [Display Devices], UMDisplayDriver_Dx11param_Structs_4eedfbd5-b87d-42bb-9ec9-2efc75ad3464.xml, d3d10umddi/D3D11DDI_HANDLESIZE, display.d3d11ddi_handlesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_HANDLESIZE is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	D3D11DDI_HANDLESIZE
product: Windows
targetos: Windows
req.typenames: D3D11DDI_HANDLESIZE
---

# D3D11DDI_HANDLESIZE structure
The D3D11DDI_HANDLESIZE structure describes a handle.

## Syntax
```
typedef struct D3D11DDI_HANDLESIZE {
  D3D11DDI_HANDLETYPE HandleType;
  SIZE_T              DriverPrivateSize;
};
```

## Members


`HandleType`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff542152">D3D11DDI_HANDLETYPE</a>-typed value that identifies the handle type.

`DriverPrivateSize`

[in] The size, in bytes, of the driver-private memory space that holds the handle data.

## Remarks
The driver's <a href="https://msdn.microsoft.com/0ddaec86-79e6-4d09-8403-6588b35f8b0f">CheckDeferredContextHandleSizes</a> function verifies the size of the driver-private memory space that holds the handle data of a deferred context handle and returns the size in the <b>DriverPrivateSize</b> member of the D3D11DDI_HANDLESIZE structure that the <i>pHandleSize</i> parameter points to.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D11DDI_HANDLESIZE is supported beginning with the Windows 7 operating system. D3D11DDI_HANDLESIZE is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/0ddaec86-79e6-4d09-8403-6588b35f8b0f">CheckDeferredContextHandleSizes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542152">D3D11DDI_HANDLETYPE</a>