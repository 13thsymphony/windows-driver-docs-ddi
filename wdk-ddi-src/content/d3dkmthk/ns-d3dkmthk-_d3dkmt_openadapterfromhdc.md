---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMHDC
title: "_D3DKMT_OPENADAPTERFROMHDC"
author: windows-driver-content
description: The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromhdc.htm
old-project: display
ms.assetid: db425b8c-4abd-4998-89bb-f6d9f066a3f6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_OPENADAPTERFROMHDC, D3DKMT_OPENADAPTERFROMHDC structure [Display Devices], OpenGL_Structs_a4c2aa1b-b17c-4e81-a0d2-9776cec61112.xml, _D3DKMT_OPENADAPTERFROMHDC, d3dkmthk/D3DKMT_OPENADAPTERFROMHDC, display.d3dkmt_openadapterfromhdc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_OPENADAPTERFROMHDC
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENADAPTERFROMHDC
---

# _D3DKMT_OPENADAPTERFROMHDC structure
The D3DKMT_OPENADAPTERFROMHDC structure describes the mapping of a device context handle (HDC) to a graphics adapter handle and monitor output.

## Syntax
```
typedef struct _D3DKMT_OPENADAPTERFROMHDC {
  HDC                            hDc;
  D3DKMT_HANDLE                  hAdapter;
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_OPENADAPTERFROMHDC;
```

## Members


`hDc`

[in] The HDC for the graphics adapter and monitor output that are retrieved.

`hAdapter`

[out] A handle to the graphics adapter for the HDC that <b>hDc</b> specifies. The adapter handle is returned from the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547047">D3DKMTOpenAdapterFromHdc</a> function.

`AdapterLuid`

[out] The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) of the graphics adapter for the HDC that <b>hDc</b> specifies. The LUID is returned from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547047">D3DKMTOpenAdapterFromHdc</a> call.

`VidPnSourceId`

[out] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the HDC that <b>hDc</b> specifies. The identification number is returned from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547047">D3DKMTOpenAdapterFromHdc</a> call.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547047">D3DKMTOpenAdapterFromHdc</a>