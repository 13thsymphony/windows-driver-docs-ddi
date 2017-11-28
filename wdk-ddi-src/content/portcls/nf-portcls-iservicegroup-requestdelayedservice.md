---
UID: NF.portcls.IServiceGroup.RequestDelayedService
title: IServiceGroup::RequestDelayedService
author: windows-driver-content
description: The RequestDelayedService method requests service after the specified delay.
old-location: audio\iservicegroup_requestdelayedservice.htm
old-project: audio
ms.assetid: 045a6c20-2e4e-4669-953d-f8648bf2d718
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: IServiceGroup, RequestDelayedService, IServiceGroup::RequestDelayedService
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IServiceGroup.RequestDelayedService
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: IServiceGroup
---

# IServiceGroup::RequestDelayedService method



## -description
<p>The <code>RequestDelayedService</code> method requests service after the specified delay.</p>


## -syntax

````
void RequestDelayedService(
  [in] ULONGLONG ulDelay
);
````


## -parameters
<dl>

### -param <i>ulDelay</i> [in]

<dd>
<p>Specifies the absolute or relative time at which the timer is to expire. If the value of <i>ulDelay</i> is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Before calling <code>RequestDelayedService</code> to request a timer delay, initialize the timer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537004">IServiceGroup::SupportDelayedService</a>.</p>

<p>Before calling <code>RequestDelayedService</code> to request a timer delay, initialize the timer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537004">IServiceGroup::SupportDelayedService</a>.</p>

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
<dt>Portcls.h (include Portcls.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537004">IServiceGroup::SupportDelayedService</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IServiceGroup::RequestDelayedService method%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
