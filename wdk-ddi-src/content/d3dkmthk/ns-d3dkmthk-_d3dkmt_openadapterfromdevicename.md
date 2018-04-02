---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMDEVICENAME
title: "_D3DKMT_OPENADAPTERFROMDEVICENAME"
author: windows-driver-content
description: The D3DKMT_OPENADAPTERFROMDEVICENAME structure describes the mapping of the given name of a device to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromdevicename.htm
old-project: display
ms.assetid: 4e633c7c-fd88-4b8f-9d29-2c7a3daa3d32
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_OPENADAPTERFROMDEVICENAME, D3DKMT_OPENADAPTERFROMDEVICENAME structure [Display Devices], OpenGL_Structs_f710fec6-a0f4-4b86-b4ba-5f8411deb490.xml, _D3DKMT_OPENADAPTERFROMDEVICENAME, d3dkmthk/D3DKMT_OPENADAPTERFROMDEVICENAME, display.d3dkmt_openadapterfromdevicename
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
-	D3DKMT_OPENADAPTERFROMDEVICENAME
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_OPENADAPTERFROMDEVICENAME
---

# _D3DKMT_OPENADAPTERFROMDEVICENAME structure
The D3DKMT_OPENADAPTERFROMDEVICENAME structure describes the mapping of the given name of a device to a graphics adapter handle and monitor output.

## Syntax
```
typedef struct _D3DKMT_OPENADAPTERFROMDEVICENAME {
  PCWSTR        pDeviceName;
  D3DKMT_HANDLE hAdapter;
  LUID          AdapterLuid;
} D3DKMT_OPENADAPTERFROMDEVICENAME;
```

## Members


`pDeviceName`

[in] A Null-terminated string that contains the name of the device from which to open an adapter instance.

`hAdapter`

[out] A handle to the graphics adapter for the device that <b>pDeviceName</b> specifies. The adapter handle is returned from the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547033">D3DKMTOpenAdapterFromDeviceName</a> function.

`AdapterLuid`

[out] The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) of the graphics adapter for the device that <b>pDeviceName</b> specifies. The LUID is returned from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547033">D3DKMTOpenAdapterFromDeviceName</a> call.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547033">D3DKMTOpenAdapterFromDeviceName</a>