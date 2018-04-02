---
UID: NS:d3dkmthk._D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
title: "_D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME"
author: windows-driver-content
description: Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID.
old-location: display\d3dkmt_queryremotevidpnsourcefromgdidisplayname.htm
old-project: display
ms.assetid: ac0ec68a-1f2c-4a39-bf88-0e69d50b1279
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure [Display Devices], _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, d3dkmthk/D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, display.d3dkmt_queryremotevidpnsourcefromgdidisplayname
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
---

# _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME structure
Describes information that is required to map a GDI display name to a remote video present network (VidPN) source ID.

## Syntax
```
typedef struct _D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME {
  WCHAR                          DeviceName[32];
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME;
```

## Members


`DeviceName`

[in] The name of the GDI device on which to open an adapter instance.

`VidPnSourceId`

[out] The zero-based video present network (VidPN) source identifier for the display device that is represented by the <b>DeviceName</b> member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439442">D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName</a>