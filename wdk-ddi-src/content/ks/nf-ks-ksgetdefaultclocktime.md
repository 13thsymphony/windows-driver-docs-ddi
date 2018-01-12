---
UID: NF:ks.KsGetDefaultClockTime
title: KsGetDefaultClockTime function
author: windows-driver-content
description: The KsGetDefaultClockTime function gets the current time of the clock.The function can be called at DISPATCH_LEVEL.
old-location: stream\ksgetdefaultclocktime.htm
old-project: stream
ms.assetid: 9689b9f8-e5ae-4689-90b1-6d029408f876
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGetDefaultClockTime
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
req.alt-api: KsGetDefaultClockTime
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
req.typenames: 
---

# KsGetDefaultClockTime function



## -description
The <b>KsGetDefaultClockTime</b> function gets the current time of the clock.

The function can be called at DISPATCH_LEVEL.



## -syntax

````
LONGLONG KsGetDefaultClockTime(
  _In_ PKSDEFAULTCLOCK DefaultClock
);
````


## -parameters

### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent. 


## -returns
The <b>KsGetDefaultClockTime</b> function returns the current clock time.


## -remarks


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
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kssetdefaultclocktime.md">KsSetDefaultClockTime</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetDefaultClockTime function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

