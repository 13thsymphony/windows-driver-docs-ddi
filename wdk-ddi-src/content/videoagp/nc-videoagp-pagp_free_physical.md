---
UID: NC:videoagp.PAGP_FREE_PHYSICAL
title: PAGP_FREE_PHYSICAL
author: windows-driver-content
description: The AgpFreePhysical function frees system memory that was committed by a previous call to AgpCommitPhysical.
old-location: display\agpfreephysical.htm
old-project: display
ms.assetid: bb0e3330-5601-47dd-afc6-94a70b42daaf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.agpfreephysical, AgpFreePhysical callback function [Display Devices], AgpFreePhysical, PAGP_FREE_PHYSICAL, PAGP_FREE_PHYSICAL, videoagp/AgpFreePhysical, VideoPort_Functions_cc6360b5-12f9-4c49-bb06-d86ada229b9e.xml
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
-	AgpFreePhysical
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---


# PAGP_FREE_PHYSICAL callback function
The <b>AgpFreePhysical</b> function frees system memory that was committed by a previous call to <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>.

## Syntax

```
PAGP_FREE_PHYSICAL PagpFreePhysical;

void PagpFreePhysical(
  IN PVOID HwDeviceExtension,
  IN PVOID PhysicalReserveContext,
  IN ULONG Pages,
  IN ULONG Offset
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the device extension of the miniport driver.

`PhysicalReserveContext`

Identifies a reserved physical address range. This context handle was obtained from <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>.

`Pages`

Specifies the number of pages of system memory that the video port driver should unmap.

`Offset`

Specifies the page offset into the reserved physical address range identified by <b>PhysicalReserveContext</b> that indicates the actual base address at which to unmap system memory.


## Return Value

None

## Remarks

When a miniport driver calls <b>AgpFreePhysical</b>, <b>Pages</b> pages of physical memory are unlocked and unmapped from the AGP-decodable physical address range. This range begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The miniport driver must specify that the exact offset and number of pages be freed as were committed in a prior call to <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | videoagp.h (include Video.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\videoagp\nc-videoagp-pagp_release_physical.md">AgpReleasePhysical</a>



<a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_FREE_PHYSICAL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>