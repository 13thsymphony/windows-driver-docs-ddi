---
UID: NS:d3dkmthk._D3DKMT_WAITFORVERTICALBLANKEVENT
title: "_D3DKMT_WAITFORVERTICALBLANKEVENT"
author: windows-driver-content
description: The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur.
old-location: display\d3dkmt_waitforverticalblankevent.htm
old-project: display
ms.assetid: dde8ebf7-7839-4bcc-8cb1-02a5ca922792
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_WAITFORVERTICALBLANKEVENT, D3DKMT_WAITFORVERTICALBLANKEVENT structure [Display Devices], OpenGL_Structs_1072adb2-825b-4fee-a84a-b958e3d2e4d4.xml, _D3DKMT_WAITFORVERTICALBLANKEVENT, d3dkmthk/D3DKMT_WAITFORVERTICALBLANKEVENT, display.d3dkmt_waitforverticalblankevent
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
-	D3DKMT_WAITFORVERTICALBLANKEVENT
product: Windows
targetos: Windows
req.typenames: D3DKMT_WAITFORVERTICALBLANKEVENT
---

# _D3DKMT_WAITFORVERTICALBLANKEVENT structure
The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur.

## Syntax
````
typedef struct _D3DKMT_WAITFORVERTICALBLANKEVENT {
  D3DKMT_HANDLE                  hAdapter;
  D3DKMT_HANDLE                  hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_WAITFORVERTICALBLANKEVENT;
````

## Members


`hAdapter`

[in] A handle to the adapter.

`hDevice`

[in] A handle to the display device. This member is optionally specified. However, if the OpenGL ICD specifies the display device, the kernel is given more optimization opportunities with regard to power usage.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the VidPN source.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforverticalblankevent.md">D3DKMTWaitForVerticalBlankEvent</a>