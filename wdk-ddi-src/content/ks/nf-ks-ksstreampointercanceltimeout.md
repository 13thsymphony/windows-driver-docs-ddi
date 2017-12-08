---
UID: NF.ks.KsStreamPointerCancelTimeout
title: KsStreamPointerCancelTimeout function
author: windows-driver-content
description: The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer.
old-location: stream\ksstreampointercanceltimeout.htm
old-project: stream
ms.assetid: 9e1dd010-0074-45fb-b3cb-f8ea7ad15e02
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsStreamPointerCancelTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsStreamPointerCancelTimeout
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# KsStreamPointerCancelTimeout function



## -description
The<b> KsStreamPointerCancelTimeout </b>function cancels a previously scheduled time-out callback on the specified stream pointer.


## -syntax

````
void KsStreamPointerCancelTimeout(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters

### -param StreamPointer [in]

A pointer to a <a href="stream.ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer for which to cancel a registered time-out callback.

## -returns
None

## -remarks
Minidrivers should use <a href="stream.ksstreampointerscheduletimeout">KsStreamPointerScheduleTimeout</a> to schedule a time-out callback on a specified stream pointer.

The <b>KsStreamPointerCancelTimeout</b> function does not affect stream pointers that have no currently scheduled time-out callback.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksstreampointerscheduletimeout">KsStreamPointerScheduleTimeout</a>
</dt>
<dt>
<a href="stream.kspingetfirstclonestreampointer">KsPinGetFirstCloneStreamPointer</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerCancelTimeout function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
