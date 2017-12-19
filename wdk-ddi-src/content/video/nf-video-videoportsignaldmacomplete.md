---
UID: NF.video.VideoPortSignalDmaComplete
title: VideoPortSignalDmaComplete function
author: windows-driver-content
description: The VideoPortSignalDmaComplete function is obsolete in Windows 2000 and later.VideoPortSignalDmaComplete indicates to the video miniport driver whether the current DMA transfer is complete.
old-location: display\videoportsignaldmacomplete.htm
old-project: display
ms.assetid: 81730acb-ff15-438d-8225-125283f61db2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: VideoPortSignalDmaComplete
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
req.alt-api: VideoPortSignalDmaComplete
req.alt-loc: Videoprt.sys
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
req.product: Windows 10 or later.
---

# VideoPortSignalDmaComplete function



## -description
The <b>VideoPortSignalDmaComplete</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortSignalDmaComplete</b> indicates to the video miniport driver whether the current DMA transfer is complete.



## -syntax

````
BOOLEAN VideoPortSignalDmaComplete(
  _In_ PVOID HwDeviceExtension,
  _In_ PDMA  pDmaHandle
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDmaHandle [in]

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="display.videoportlockpages">VideoPortLockPages</a> returns. 


## -returns
<b>VideoPortSignalDmaComplete</b> always returns <b>FALSE</b>.


## -remarks
See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
</table>