---
UID: NF.video.VideoPortSetDmaContext
title: VideoPortSetDmaContext function
author: windows-driver-content
description: The VideoPortSetDmaContext function is obsolete in Windows 2000 and later.
old-location: display\videoportsetdmacontext.htm
old-project: display
ms.assetid: 4f357612-c07d-42fe-a49f-59acec80a8bc
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortSetDmaContext
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
req.alt-api: VideoPortSetDmaContext
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

# VideoPortSetDmaContext function



## -description
The <b>VideoPortSetDmaContext</b> function is <b>obsolete</b> in Windows 2000 and later. 


## -syntax

````
VOID VideoPortSetDmaContext(
  _In_  PVOID HwDeviceExtension,
  _Out_ PDMA  pDma,
  _In_  PVOID InstanceContext
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param pDma [out]

Pointer to a DMA handle. 

### -param InstanceContext [in]

Pointer to the DMA context to set.

## -returns
None

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