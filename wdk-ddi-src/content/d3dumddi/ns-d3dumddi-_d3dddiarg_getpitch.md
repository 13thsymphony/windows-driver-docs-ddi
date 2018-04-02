---
UID: NS:d3dumddi._D3DDDIARG_GETPITCH
title: "_D3DDDIARG_GETPITCH"
author: windows-driver-content
description: The D3DDDIARG_GETPITCH structure describes an encrypted surface for which the GetPitch function retrieves the pitch.
old-location: display\d3dddiarg_getpitch.htm
old-project: display
ms.assetid: 59661cfe-4a1f-4805-9421-7f694e82f8d2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_GETPITCH, D3DDDIARG_GETPITCH structure [Display Devices], UMDisplayDriver_param_Structs_02e95329-8eba-41a3-ae4e-d8830b47ada6.xml, _D3DDDIARG_GETPITCH, d3dumddi/D3DDDIARG_GETPITCH, display.d3dddiarg_getpitch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_GETPITCH is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_GETPITCH
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_GETPITCH
---

# _D3DDDIARG_GETPITCH structure
The D3DDDIARG_GETPITCH structure describes an encrypted surface for which the <a href="https://msdn.microsoft.com/1a5721a3-c03f-4827-9626-c9b6af5059a1">GetPitch</a> function retrieves the pitch.

## Syntax
```
typedef struct _D3DDDIARG_GETPITCH {
  HANDLE hCryptoSession;
  HANDLE hResource;
  UINT   SubResourceIndex;
  UINT   Pitch;
} D3DDDIARG_GETPITCH;
```

## Members


`hCryptoSession`

[in] A handle to the encryption session.

`hResource`

[in] A handle to the resource.

`SubResourceIndex`

[in] The zero-based index into the resource, which the <b>hResource</b> handle specifies. This index indicates the encrypted surface.

`Pitch`

[out] The pitch, in bytes, of the encrypted surface. The user-mode display driver's <a href="https://msdn.microsoft.com/1a5721a3-c03f-4827-9626-c9b6af5059a1">GetPitch</a> function returns this pitch value to the Direct3D runtime.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDIARG_GETPITCH is supported beginning with the Windows 7 operating system. D3DDDIARG_GETPITCH is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/1a5721a3-c03f-4827-9626-c9b6af5059a1">GetPitch</a>