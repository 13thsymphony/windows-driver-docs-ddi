---
UID: NF.video.VideoPortFreeCommonBuffer
title: VideoPortFreeCommonBuffer function
author: windows-driver-content
description: The VideoPortFreeCommonBuffer function is obsolete and is supported only for backward compatibility with existing drivers.
old-location: display\videoportfreecommonbuffer.htm
old-project: display
ms.assetid: 8725868e-00bc-45fe-ab9d-c192abd1a059
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortFreeCommonBuffer
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
req.alt-api: VideoPortFreeCommonBuffer
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# VideoPortFreeCommonBuffer function



## -description
The <b>VideoPortFreeCommonBuffer</b> function is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="display.videoportreleasecommonbuffer">VideoPortReleaseCommonBuffer</a>.
<b>VideoPortFreeCommonBuffer</b> deallocates system memory that was allocated by a call to <a href="display.videoportgetcommonbuffer">VideoPortGetCommonBuffer</a>.


## -syntax

````
VOID VideoPortFreeCommonBuffer(
  _In_ PVOID            HwDeviceExtension,
  _In_ ULONG            Length,
  _In_ PVOID            VirtualAddress,
  _In_ PHYSICAL_ADDRESS LogicalAddress,
  _In_ BOOLEAN          CacheEnabled
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param Length [in]

Specifies the number of bytes of memory to be freed.

### -param VirtualAddress [in]

Pointer to the corresponding virtual address of the allocated memory range.

### -param LogicalAddress [in]

Specifies the logical address of the buffer to be freed.

### -param CacheEnabled [in]

Indicates whether the allocated memory is cached.

## -returns
None

## -remarks
Except for <a href="display.videoportgetcommonbuffer">VideoPortGetCommonBuffer's </a><i>Alignment</i> parameter, all of the parameters used in a call to <b>VideoPortFreeCommonBuffer</b> must have the same values as those used in the previous call to <b>VideoPortGetCommonBuffer</b>.

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
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.videoportreleasecommonbuffer">VideoPortReleaseCommonBuffer</a>
</dt>
<dt>
<a href="display.videoportgetcommonbuffer">VideoPortGetCommonBuffer</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortFreeCommonBuffer function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
