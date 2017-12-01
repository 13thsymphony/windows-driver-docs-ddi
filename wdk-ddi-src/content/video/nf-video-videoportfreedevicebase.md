---
UID: NF.video.VideoPortFreeDeviceBase
title: VideoPortFreeDeviceBase
author: windows-driver-content
description: The VideoPortFreeDeviceBase function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling VideoPortGetDeviceBase.
old-location: display\videoportfreedevicebase.htm
old-project: display
ms.assetid: 5b165237-f6fb-449c-878d-0ee09076d203
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VideoPortFreeDeviceBase
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
req.alt-api: VideoPortFreeDeviceBase
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
req.iface: 
req.product: Windows 10 or later.
---

# VideoPortFreeDeviceBase function



## -description
<p>The <b>VideoPortFreeDeviceBase</b> function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.</p>


## -syntax

````
VOID VideoPortFreeDeviceBase(
   PVOID HwDeviceExtension,
   PVOID MappedAddress
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>Pointer to the miniport driver's device extension.</p>
</dd>

### -param <i>MappedAddress</i> 

<dd>
<p>Specifies the base address of the mapped range to be freed. This value must be the same as the value returned by a preceding call to <b>VideoPortGetDeviceBase</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><b>VideoPortFreeDeviceBase</b> must be called from the miniport driver's <a href="..\video\nc-video-pvideo-hw-find-adapter.md">HwVidFindAdapter</a> function if the miniport driver has already mapped an address range for an adapter it cannot support or does not use any longer.</p>

<p>When this occurs, the miniport driver also must release its claim on the corresponding hardware resources in the registry. To release all claims on resources for a particular adapter, call <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> or <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> with the <i>NumAccessRanges</i> parameter set to zero. To release claims on selected access ranges, do the following:</p>

<p>Modify the access ranges array of claimed bus-relative ranges for the adapter by setting the appropriate elements' <b>RangeLength</b>(s) to zero. Leave the current specification as is in all elements on which the miniport driver will not release its claims.</p>

<p>Call <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> with this modified <i>AccessRanges</i> array.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo-hw-find-adapter.md">HwVidFindAdapter</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortFreeDeviceBase function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
