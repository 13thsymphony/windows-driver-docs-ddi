---
UID: NS:d3dkmddi._DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
title: "_DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS"
author: windows-driver-content
description: Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.
old-location: display\dxgkargcb_present_displayonly_progress.htm
old-project: display
ms.assetid: c3849df0-0794-43fe-ba29-6daa8461cd9a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure [Display Devices], _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, d3dkmddi/DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, display.dxgkargcb_present_displayonly_progress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
---

# _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure
Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.

## Syntax
```
typedef struct _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID        VidPnSourceId;
  DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID ProgressId;
} DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS;
```

## Members


`VidPnSourceId`

An integer that identifies a video present source.

`ProgressId`

A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh464079">DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID</a> that represents the status of the current present operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh464079">DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID</a>