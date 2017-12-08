---
UID: NF.ks.KsStreamPointerScheduleTimeout
title: KsStreamPointerScheduleTimeout function
author: windows-driver-content
description: The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer.
old-location: stream\ksstreampointerscheduletimeout.htm
old-project: stream
ms.assetid: 143c4ca2-91ae-49c3-80e0-e7959e4bd297
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsStreamPointerScheduleTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsStreamPointerScheduleTimeout
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

# KsStreamPointerScheduleTimeout function



## -description
The<b> KsStreamPointerScheduleTimeout </b>function registers a timeout callback with AVStream for the given stream pointer.


## -syntax

````
void KsStreamPointerScheduleTimeout(
  _In_ PKSSTREAM_POINTER  StreamPointer,
  _In_ PFNKSSTREAMPOINTER Callback,
  _In_ ULONGLONG          Interval
);
````


## -parameters

### -param StreamPointer [in]

A pointer to a <a href="stream.ksstream_pointer">KSSTREAM_POINTER</a> structure representing the stream pointer for which to register a timeout.

### -param Callback [in]

A pointer to a minidriver-supplied <a href="stream.avstrminitimeoutcallback">AVStrMiniTimeoutCallback</a> routine. If the stream pointer has not been deleted or the timeout canceled before the interval expires, AVStream calls this routine immediately following expiration of the interval.

### -param Interval [in]

Specifies the interval in 100-nanosecond units from the current time to the time that the timeout occurs.

## -returns
None

## -remarks
It is safe to call <b>KsStreamPointerScheduleTimeout</b> on a stream pointer that already has a timeout scheduled. In this case, AVStream cancels the previous timeout and replaces it with the new timeout.
<p class="note">Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.

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
<a href="stream.ksstreampointercanceltimeout">KsStreamPointerCancelTimeout</a>
</dt>
<dt>
<a href="stream.ksstreampointerdelete">KsStreamPointerDelete</a>
</dt>
<dt>
<a href="stream.ksstream_pointer">KSSTREAM_POINTER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerScheduleTimeout function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
