---
UID: NC:videoagp.PAGP_RELEASE_PHYSICAL
title: PAGP_RELEASE_PHYSICAL
author: windows-driver-content
description: The AgpReleasePhysical function frees a physical address range reserved by a previous call to AgpReservePhysical.
old-location: display\agpreleasephysical.htm
old-project: display
ms.assetid: 4da0f5cb-a017-4df5-958b-c76b7a08495a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.agpreleasephysical, AgpReleasePhysical callback function [Display Devices], AgpReleasePhysical, PAGP_RELEASE_PHYSICAL, PAGP_RELEASE_PHYSICAL, videoagp/AgpReleasePhysical, VideoPort_Functions_427923a7-3205-41a7-a470-dbc7d531e47f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	videoagp.h
apiname:
-	AgpReleasePhysical
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---


# PAGP_RELEASE_PHYSICAL callback function
The <b>AgpReleasePhysical</b> function frees a physical address range reserved by a previous call to <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>.

## Syntax

```
PAGP_RELEASE_PHYSICAL PagpReleasePhysical;

void PagpReleasePhysical(
  IN PVOID HwDeviceExtension,
  IN PVOID PhysicalReserveContext
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`PhysicalReserveContext`

Is the context handle that identifies the reserved physical address range to be released. This context was obtained from <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>.


## Return Value

None

## Remarks

The miniport driver must call <a href="..\videoagp\nc-videoagp-pagp_free_physical.md">AgpFreePhysical</a> to unmap all committed memory within the address range identified by <b>PhysicalReserveContext</b> before calling <b>AgpReleasePhysical</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems. Available in Windows 2000 and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | videoagp.h (include Video.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>

<a href="..\videoagp\nc-videoagp-pagp_free_physical.md">AgpFreePhysical</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_RELEASE_PHYSICAL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>