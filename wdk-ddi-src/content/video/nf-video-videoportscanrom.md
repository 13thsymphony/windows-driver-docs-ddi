---
UID: NF.video.VideoPortScanRom
title: VideoPortScanRom
author: windows-driver-content
description: The VideoPortScanRom function is obsolete in Windows XP and later versions. It is supported only for backward compatibility. VideoPortScanRom performs a case-sensitive search for a specified string in ROM.
old-location: display\videoportscanrom.htm
old-project: display
ms.assetid: 7787237c-5afd-46f2-ac75-6c0b41d37352
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VideoPortScanRom
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
req.alt-api: VideoPortScanRom
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

# VideoPortScanRom function



## -description
<p>The <b>VideoPortScanRom</b> function is <b>obsolete</b> in Windows XP and later versions. It is supported only for backward compatibility. </p>
<p><b>VideoPortScanRom</b> performs a case-sensitive search for a specified string in ROM.</p>


## -syntax

````
BOOLEAN VideoPortScanRom(
   PVOID  HwDeviceExtension,
   PUCHAR RomBase,
   ULONG  RomLength,
   PUCHAR String
);
````


## -parameters
<dl>

### -param HwDeviceExtension 

<dd>
<p>Pointer to the miniport driver's device extension.</p>
</dd>

### -param RomBase 

<dd>
<p>Specifies the base ROM address at which the search should start. The given <i>RomBase</i> must be in a mapped range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.</p>
</dd>

### -param RomLength 

<dd>
<p>Specifies the size in bytes of the mapped ROM to be searched.</p>
</dd>

### -param String 

<dd>
<p>Pointer to the driver-allocated string to search for.</p>
</dd>
</dl>

## -returns
<p>If the string is found, <b>VideoPortScanRom</b> returns <b>TRUE</b>. Otherwise, it returns <b>FALSE</b>.</p>

## -remarks
<p><b>VideoPortScanRom</b> cannot be called from a miniport driver's <a href="..\video\nc-video-pvideo-hw-interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pvideo-hw-timer.md">HwVidTimer</a> functions, or from <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>, or from a callback to <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>. </p>

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
<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetromimage.md">VideoPortGetRomImage</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortScanRom function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
