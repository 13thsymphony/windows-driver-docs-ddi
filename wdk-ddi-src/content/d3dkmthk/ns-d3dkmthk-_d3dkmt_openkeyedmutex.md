---
UID: NS:d3dkmthk._D3DKMT_OPENKEYEDMUTEX
title: "_D3DKMT_OPENKEYEDMUTEX"
author: windows-driver-content
description: The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the D3DKMTOpenKeyedMutex function opens.
old-location: display\d3dkmt_openkeyedmutex.htm
old-project: display
ms.assetid: c5200822-b393-4ba1-8d2a-d4ab98ffcf1d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_OPENKEYEDMUTEX, D3DKMT_OPENKEYEDMUTEX structure [Display Devices], OpenGL_Structs_78a96126-b992-431f-9e91-c08c61694732.xml, _D3DKMT_OPENKEYEDMUTEX, d3dkmthk/D3DKMT_OPENKEYEDMUTEX, display.d3dkmt_openkeyedmutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_OPENKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_OPENKEYEDMUTEX
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENKEYEDMUTEX
---

# _D3DKMT_OPENKEYEDMUTEX structure
The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547054">D3DKMTOpenKeyedMutex</a> function opens.

## Syntax
```
typedef struct _D3DKMT_OPENKEYEDMUTEX {
  D3DKMT_HANDLE hSharedHandle;
  D3DKMT_HANDLE hKeyedMutex;
} D3DKMT_OPENKEYEDMUTEX;
```

## Members


`hSharedHandle`

[in] A D3DKMT_HANDLE data type that represents a kernel-mode shared global handle to the keyed mutex object.

`hKeyedMutex`

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object in the current process.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMT_OPENKEYEDMUTEX is supported beginning with the Windows 7 operating system. D3DKMT_OPENKEYEDMUTEX is supported beginning with the Windows 7 operating system. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547054">D3DKMTOpenKeyedMutex</a>