---
UID: NS:d3dkmddi._DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
title: "_DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS"
author: windows-driver-content
description: Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.
old-location: display\dxgkargcb_present_displayonly_progress.htm
old-project: display
ms.assetid: c3849df0-0794-43fe-ba29-6daa8461cd9a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkargcb_present_displayonly_progress, DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, d3dkmddi/DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
---

# _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure
Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.

## Syntax
````
typedef struct _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID        VidPnSourceId;
  DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID ProgressId;
} DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS;
````

## Members


`ProgressId`

A value of type <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_present_display_only_progress_id.md">DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID</a> that represents the status of the current present operation.

`VidPnSourceId`

An integer that identifies a video present source.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_present_display_only_progress_id.md">DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>