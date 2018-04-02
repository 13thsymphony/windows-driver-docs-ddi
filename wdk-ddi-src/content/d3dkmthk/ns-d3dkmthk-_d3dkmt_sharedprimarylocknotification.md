---
UID: NS:d3dkmthk._D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
title: "_D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION"
author: windows-driver-content
description: The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock.
old-location: display\d3dkmt_sharedprimarylocknotification.htm
old-project: display
ms.assetid: 4e7766bb-eb5b-4f79-b9b8-89f7dcb98569
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure [Display Devices], OpenGL_Structs_4ec11480-30cb-45a1-a31c-e7432ec45abf.xml, _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, d3dkmthk/D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, display.d3dkmt_sharedprimarylocknotification
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
-	D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
---

# _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure
The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock.

## Syntax
```
typedef struct _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION {
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  RECTL                          LockRect;
} D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION;
```

## Members


`AdapterLuid`

[in] The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) of the graphics adapter on which the GDI shared primary surface exists.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which the GDI shared primary surface exists.

`LockRect`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the shared primary surface; the operating system disables all sprites that intersect with this rectangle. If the OpenGL ICD specifies zero for each member of RECTL, the operating system disables all sprites on the shared primary surface.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547208">D3DKMTSharedPrimaryLockNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a>