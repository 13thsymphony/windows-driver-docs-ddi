---
UID: NS:d3dkmddi._DXGK_PRESENTMULTIPLANEOVERLAYINFO
title: "_DXGK_PRESENTMULTIPLANEOVERLAYINFO"
author: windows-driver-content
description: Specifies info on a VidPN input and an overlay plane to display.
old-location: display\dxgk_presentmultiplaneoverlayinfo.htm
old-project: display
ms.assetid: b9cc78f3-b8b5-4a54-87b2-321b75ed9a21
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_PRESENTMULTIPLANEOVERLAYINFO, DXGK_PRESENTMULTIPLANEOVERLAYINFO structure [Display Devices], _DXGK_PRESENTMULTIPLANEOVERLAYINFO, d3dkmddi/DXGK_PRESENTMULTIPLANEOVERLAYINFO, display.dxgk_presentmultiplaneoverlayinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_PRESENTMULTIPLANEOVERLAYINFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_PRESENTMULTIPLANEOVERLAYINFO
---

# _DXGK_PRESENTMULTIPLANEOVERLAYINFO structure
Specifies info on a VidPN input and an overlay plane to display.

## Syntax
```
typedef struct _DXGK_PRESENTMULTIPLANEOVERLAYINFO {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID    VidPnSourceId;
  UINT                              PlaneListCount;
  DXGK_PRESENTMULTIPLANEOVERLAYLIST *pPlaneList;
} DXGK_PRESENTMULTIPLANEOVERLAYINFO;
```

## Members


`VidPnSourceId`

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.

`PlaneListCount`

[in] The number of overlay planes that are available to display.

`pPlaneList`

[in] A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh780312">DXGK_PRESENTMULTIPLANEOVERLAYLIST</a> that describes the overlay plane to display.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh780312">DXGK_PRESENTMULTIPLANEOVERLAYLIST</a>