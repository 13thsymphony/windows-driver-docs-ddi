---
UID: NF:video.VideoPortLockPages
title: VideoPortLockPages function
author: windows-driver-content
description: The VideoPortLockPages function is obsolete in Windows 2000 and later. Use VideoPortLockBuffer in place of this function.VideoPortLockPages locks the specified virtual memory and possibly performs part or all of a DMA transfer.
old-location: display\videoportlockpages.htm
old-project: display
ms.assetid: f5e06ff3-98ba-4443-8ea6-c32b063cd478
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortLockPages, VideoPortLockPages function [Display Devices], VideoPort_Functions_47b202e0-2a8b-4fb0-9cf2-b4ef3ddb9ff4.xml, display.videoportlockpages, video/VideoPortLockPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortLockPages
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortLockPages function
The <b>VideoPortLockPages</b> function is <b>obsolete</b> in Windows 2000 and later. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570326">VideoPortLockBuffer</a> in place of this function.

<b>VideoPortLockPages</b> locks the specified virtual memory and possibly performs part or all of a DMA transfer.

## Syntax

```
VIDEOPORT_API BOOLEAN VideoPortLockPages(
  IN PVOID                     HwDeviceExtension,
  IN OUT PVIDEO_REQUEST_PACKET pVrp,
  IN PEVENT                    pUEvent,
  IN PEVENT                    pDisplayEvent,
  IN DMA_FLAGS                 DmaFlags
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pVrp`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570547">VIDEO_REQUEST_PACKET</a> structure. The miniport driver must have set <b>InputBuffer</b> and <b>InputBufferLength</b> to contain the virtual address and the size in bytes, respectively, of the memory to be locked for the transfer. This memory was allocated by the display driver and passed to the miniport driver through an IOCTL. The video port returns a pointer to and the size in bytes of the scatter/gather list in <b>OutputBuffer</b> and <b>OutputBufferLength</b>, respectively.

`pUEvent`

Pointer to a mapped user event that is to be set by the miniport driver, or <b>NULL</b>. The user event was mapped by the display driver and passed to the miniport driver through an IOCTL.

`pDisplayEvent`

Pointer to an event that is to be set by the miniport driver, or <b>NULL</b>. This event was created by and received from the display driver through an IOCTL.

`DmaFlags`

Specifies the action to be performed. This parameter must be one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>VideoPortDmaInitOnly</b>

</td>
<td>
<b>VideoPortLockPages</b> locks the requested memory.

</td>
</tr>
<tr>
<td>
<b>VideoPortKeepPagesLocked</b>

</td>
<td>
<b>VideoPortLockPages</b> takes no action.

</td>
</tr>
<tr>
<td>
<b>VideoPortUnlockAfterDma</b>

</td>
<td>
<b>VideoPortLockPages</b> takes no action.

</td>
</tr>
</table>


## Return Value

<b>VideoPortLockPages</b> returns <b>TRUE</b> upon successful completion of the action requested of it. It returns <b>FALSE</b> if the <i>DmaFlags</i> parameter is not equal to <b>VideoPortDmaInitOnly</b>.

## Remarks

See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

<b>VideoPortLockPages</b> cannot be called from an ISR or DPC.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570326">VideoPortLockBuffer</a>