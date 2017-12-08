---
UID: NF.video.VideoPortMapDmaMemory
title: VideoPortMapDmaMemory function
author: windows-driver-content
description: The VideoPortMapDmaMemory function is obsolete in Windows 2000 and later.VideoPortMapDmaMemory maps a range of memory for use in DMA transfers.
old-location: display\videoportmapdmamemory.htm
old-project: display
ms.assetid: 51148c26-c10d-4c57-9e3e-c7d82d6a1c79
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortMapDmaMemory
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
req.alt-api: VideoPortMapDmaMemory
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

# VideoPortMapDmaMemory function



## -description
The <b>VideoPortMapDmaMemory</b> function is <b>obsolete</b> in Windows 2000 and later.
<b>VideoPortMapDmaMemory</b> maps a range of memory for use in DMA transfers.


## -syntax

````
PDMA VideoPortMapDmaMemory(
  _In_    PVOID                 HwDeviceExtension,
  _In_    PVIDEO_REQUEST_PACKET pVrp,
  _In_    PHYSICAL_ADDRESS      BoardAddress,
  _In_    PULONG                Length,
  _In_    PULONG                InIoSpace,
  _In_    PVOID                 MappedUserEvent,
  _In_    PVOID                 DisplayDriverEvent,
  _Inout_ PVOID                 *VirtualAddress
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param pVrp [in]

Pointer to a <a href="display.video_request_packet">VIDEO_REQUEST_PACKET</a>.

### -param BoardAddress [in]

Specifies the adapter's beginning address.

### -param Length [in]

Specifies the length, in bytes, of the range of memory.

### -param InIoSpace [in]

Indicates the location of the range. This parameter can be one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_DENSE
</td>
<td>
Memory is densely mapped and linear.
</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_IO
</td>
<td>
The range is in system I/O space. Should not be set by the display driver.
</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_MEMORY
</td>
<td>
The range is in memory space. Should not be set by the display driver.
</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_P6CACHE
</td>
<td>
P6 MTRR caching, which is equivalent to write-combine caching. (kernel and user mode).
</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_USER_MODE
</td>
<td>
Memory pointer for application use.
</td>
</tr>
</table>
 

### -param MappedUserEvent [in]

Is reserved for system use.

### -param DisplayDriverEvent [in]

Is reserved for system use.

### -param VirtualAddress [in, out]

Is reserved for system use.

## -returns
<b>VideoPortMapDmaMemory</b> always returns <b>NULL</b>.

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