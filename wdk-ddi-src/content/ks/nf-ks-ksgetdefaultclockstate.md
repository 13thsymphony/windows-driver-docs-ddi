---
UID: NF.ks.KsGetDefaultClockState
title: KsGetDefaultClockState
author: windows-driver-content
description: The KsGetDefaultClockState function gets the current state of the clock.The function can be called at DISPATCH_LEVEL.
old-location: stream\ksgetdefaultclockstate.htm
old-project: stream
ms.assetid: b579fd85-5073-4894-a4ef-e56638f45ef6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KsGetDefaultClockState
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
req.alt-api: KsGetDefaultClockState
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
req.irql: 
req.iface: 
---

# KsGetDefaultClockState function



## -description
<p>The <b>KsGetDefaultClockState</b> function gets the current state of the clock.</p>
<p>The function can be called at DISPATCH_LEVEL.</p>


## -syntax

````
KSSTATE KsGetDefaultClockState(
  _In_ PKSDEFAULTCLOCK DefaultClock
);
````


## -parameters
<dl>

### -param DefaultClock [in]

<dd>
<p>Specifies an initialized, default clock structure that is shared among any instance of the default clock for the parent.</p>
</dd>
</dl>

## -returns
<p>The <b>KsGetDefaultClockState</b> function returns the current clock state.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kssetdefaultclockstate.md">KsSetDefaultClockState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetDefaultClockState function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
