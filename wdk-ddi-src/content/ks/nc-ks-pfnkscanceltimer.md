---
UID: NC.ks.PFNKSCANCELTIMER
title: PFNKSCANCELTIMER
author: windows-driver-content
description: A streaming minidriver's KStrCancelTimer routine is called to cancel a custom timer object that was previously specified in the SetTimer parameter in a call to KsAllocateDefaultClockEx.
old-location: stream\kstrcanceltimer.htm
old-project: stream
ms.assetid: bdfe0fc3-1b25-493f-9d70-3b6d680fde50
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrCancelTimer
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# PFNKSCANCELTIMER callback



## -description
<p>A streaming minidriver's <i>KStrCancelTimer</i> routine is called to cancel a custom timer object that was previously specified in the <i>SetTimer</i> parameter in a call to <a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a>.</p>


## -prototype

````
PFNKSCANCELTIMER KStrCancelTimer;

BOOLEAN KStrCancelTimer(
  _In_ PVOID   Context,
  _In_ PKTIMER Timer
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>Pointer to the minidriver-supplied information context. The minidriver passes the information context to <a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a> in the function's <i>DeferredContext</i> parameter when the minidriver allocates a custom DPC timer object.</p>
</dd>

### -param <i>Timer</i> [in]

<dd>
<p>Pointer to the minidriver's custom timer object to cancel.</p>
</dd>
</dl>

## -returns
<p>Returns <b>TRUE</b> if the specified timer object is in the system timer queue, or <b>FALSE</b> otherwise.</p>

## -remarks
<p>Minidrivers can optionally supply a <i>KStrCancelTimer</i> callback function as a parameter to <b>KsAllocateDefaultClockEx</b>.</p>

<p>The minidriver-supplied <i>KStrCancelTimer</i> must have the same characteristics as <a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>.</p>

<p>If a minidriver supplies a <i>KStrCancelTimer</i> callback function, the minidriver must also supply a <a href="stream.kstrsettimer">KStrSetTimer</a> callback function.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>
</dt>
<dt>
<a href="stream.kstrsettimer">KStrSetTimer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrCancelTimer routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
