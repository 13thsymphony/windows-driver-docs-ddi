---
UID: NS:d3dkmthk._D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION
title: "_D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION"
author: windows-driver-content
description: The D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION structure describes the shared primary surface that an application just unlocked.
old-location: display\d3dkmt_sharedprimaryunlocknotification.htm
old-project: display
ms.assetid: 294fe805-4dce-4d0e-b0dd-9279a1ef9514
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION, D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION structure [Display Devices], OpenGL_Structs_1766625b-9d47-4e86-9f24-08706541c167.xml, _D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION, d3dkmthk/D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION, display.d3dkmt_sharedprimaryunlocknotification
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
-	D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION
---

# _D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION structure
The D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION structure describes the shared primary surface that an application just unlocked.

## Syntax
```
typedef struct _D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION {
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION;
```

## Members


`AdapterLuid`

[in] The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) of the graphics adapter on which the GDI shared primary surface exists.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which the GDI shared primary surface exists.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547214">D3DKMTSharedPrimaryUnLockNotification</a>